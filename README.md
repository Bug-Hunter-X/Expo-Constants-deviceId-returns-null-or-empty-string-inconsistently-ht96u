# Expo Constants.deviceId Inconsistency

This repository demonstrates a bug where Expo's `Constants.deviceId` returns `null` or an empty string inconsistently.  This makes reliable device identification challenging.

## Problem

The `Constants.deviceId` property, intended to provide a unique identifier for each device, sometimes fails to return a value, even on devices where a unique ID should exist.

## Steps to Reproduce

1. Clone this repository.
2. Run the app using Expo Go or a similar method.
3. Observe the output; it might show `null` or an empty string instead of a unique device ID.

## Solution

The provided solution attempts to mitigate this issue by implementing a fallback mechanism using other identifiers (like device UUID, if available) and storing the ID persistently using AsyncStorage. This ensures a consistent ID even if `Constants.deviceId` fails.