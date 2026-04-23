# Code Review: Order Processing Module

## Problem/Feature Description

Your team is building an e-commerce backend in TypeScript. A developer has submitted a pull request that adds order processing logic — it calculates totals, applies discounts, and saves orders to the database. The change has been flagged for review before it goes to staging.

The author is a mid-level developer who tends to write working code but sometimes skips edge cases and uses overly generic variable names. Your job is to review the PR and leave written feedback in a review document that will be shared with the author.

## Output Specification

Write your complete code review to a file named `review.md`. The review should cover all aspects of the code change provided below.

## Input Files

The following file represents the code change under review. Extract it before beginning.

=============== FILE: inputs/orderProcessor.ts ===============
import { db } from './database';

interface Order {
  items: { productId: string; qty: number; price: number }[];
  customerId: string;
  couponCode?: string;
}

interface Result {
  id: string;
  total: number;
  status: string;
}

const DISCOUNTS: Record<string, number> = {
  SAVE10: 0.10,
  SAVE20: 0.20,
};

export async function process(data: Order): Promise<Result> {
  let total = 0;
  for (const x of data.items) {
    total += x.qty * x.price;
  }

  if (data.couponCode) {
    const d = DISCOUNTS[data.couponCode];
    total = total - total * d;
  }

  const record = await db.orders.create({
    customerId: data.customerId,
    total,
    status: 'pending',
  });

  return { id: record.id, total, status: record.status };
}
