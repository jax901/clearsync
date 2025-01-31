# 0001 - Asset Price Precision

## Status

In Work

## Context

In trading industry most users understand PIP, or price-points which is the number of significant digits composing a price.

In FOREX a pip is 0.1 Cent, and this is the smallest price increment. Matching engine should match using only those price steps and not lower values.

In the context of YN, we must have a network global configuration to make members join easily and have harmony of configuration, we also aim in having configless deployments or network wide configuration files using IPFS.

## Decision

Significant figures, also known as the precision of a number in positional notation, are digits in the number that are reliable and necessary to indicate the quantity of something.

The precision level of all trading prices is calculated based on significant figures. Yellow members uses seven (7) significant digits for the prices of all pairs of the network.

Some examples of five significant digits are 1.0234, 10.234, 120.34, 1234.5, 0.012345, and 0.00012340.

This is similar to how traditional global markets handle the precision of small, medium, and large values. The reasoning behind this is that the number of decimals becomes less important as the amount increases. The opposite is true for minimal amounts, where greater precision is more valuable.

## Consequences

1. All API outputting prices should be truncated and formation using seven (7) significant figures
2. All API input must reject orders where prices are lower in precision
3. All frontend and UI clients should truncate order price input to seven (7) significant figures
