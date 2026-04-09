# Code Review: Shopping Cart Module

## Problem/Feature Description

A mid-level engineer on the e-commerce platform team has submitted a pull request introducing a new `ShoppingCart` TypeScript class as part of a checkout feature rollout. The class manages adding items, removing items, and calculating totals including discount codes. The PR description says the implementation is "complete and ready to ship."

You've been asked to review the PR before it gets merged into the release branch. The checkout flow handles real money calculations, so correctness and reliability are critical.

## Output Specification

Write your code review to a file called `review.md`. Address all concerns you find in the code.

## Input Files

The following files are provided as inputs. Extract them before beginning.

=============== FILE: inputs/shopping_cart.ts ===============
interface CartItem {
  id: string;
  name: string;
  price: number;
  quantity: number;
}

const DISCOUNT_CODES: Record<string, number> = {
  SAVE10: 0.10,
  SAVE20: 0.20,
  HALFOFF: 0.50,
};

export class ShoppingCart {
  private items: CartItem[] = [];

  addItem(item: CartItem): void {
    const existing = this.items.find(i => i.id === item.id);
    if (existing) {
      existing.quantity += item.quantity;
    } else {
      this.items.push(item);
    }
  }

  removeItem(id: string): void {
    this.items = this.items.filter(i => i.id !== id);
  }

  getTotal(): number {
    return this.items.reduce((sum, item) => sum + item.price * item.quantity, 0);
  }

  applyDiscount(code: string): number {
    const rate = DISCOUNT_CODES[code];
    return this.getTotal() * (1 - rate);
  }

  getItemCount(): number {
    return this.items.reduce((sum, item) => sum + item.quantity, 0);
  }
}
