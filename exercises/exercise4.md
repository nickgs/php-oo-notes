## Exercise 4 - Configurable Engines

# Introduction
With so many different types of Vehicles our client now offers they have built a standard platform to be able to swap different engine configurations. They have contracted us to extend their current system to support engine configurations for their Cars, SuperCars, and Tractors. 

# Phase 4
## Requirements
Our client needs an EngineInterface that defines the following methods: 

1. getPower()
2. getDisplacement()
3. getCylinders()

In addition, we will need to implement 2 different types of Engines: 

1. StandardEngine
2. PerformanceEngine

The Car, SuperCar, and Tractor classes need to be modified to allow for supporting both engines but only having ONE engine at a time. 

## Deliverables
A new interface called EngineInterface declaring the methods outlined above. Two implementations of EngineInterface named StandardEngine and PerformanceEngine. Modified Car, SuperCar, and Tractor classes to support engines. Supply a test illustrating support for placing Engines into our Vehicles.

## Timeline
You have 30 minutes to deliver this work.