# Case Study: Inventory Reorder Planner

**Date:** 2025-08-29

## Overview
A lightweight Python planner that converts an orders export into **safety stock**, **reorder points**, and **MOQ-aware** recommendations.

## Approach
1) Clean orders → daily demand per SKU  
2) 28-day mean & std per SKU  
3) Service level → z-score  
4) Safety = z × std × √L; ROP = mean × L + safety; Target = mean × (L+H) + safety  
5) Recommendation = ceil(Target − on_hand) → apply MOQ/case packs  
6) Excel export (Reorder, DailyDemand, CleanOrders, ConfigUsed)
