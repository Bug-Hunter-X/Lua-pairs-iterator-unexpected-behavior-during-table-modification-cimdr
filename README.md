# Lua pairs iterator unexpected behavior during table modification

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with tables modified during iteration.  The `bug.lua` file contains code exhibiting the problem, while `bugSolution.lua` presents a solution to mitigate the unexpected behavior.

## Problem Description

Lua's `pairs` iterator iterates over the key-value pairs of a table. However, if the table is modified during iteration (elements added, removed, or keys changed), the iterator's behavior might become unpredictable, potentially leading to skipped elements or an infinite loop.

## Solution

The provided solution in `bugSolution.lua` addresses this issue by creating a copy of the table before iteration to prevent modification during the process.  This ensures that all elements are visited once and only once.  Alternative approaches might involve using `ipairs` for numerically indexed tables or carefully managing table modifications outside the iterator's scope, ensuring that mutations don't interfere with the iteration process.