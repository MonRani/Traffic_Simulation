## Traffic Simulation

# Car class

Suppose you are driving on a one-lane road of length L. Your driving is constrained by the following rules:

1. You are not allowed to exceed the maximum speed vmax.
2. Drivers seek to maximize their speed.
3. You cannot be within a minimal distance dmin from the immediate front car.
4. You cannot cross the immediate front car, as the road only has one lane.
We choose vmax = 105 km/h and dmin = 0.001 km. You can experiment with these values to explore how your model works for different settings. 
Suppose you have 5 cars: car1, car2, car3, car4, and car5. At time t, cari has a position denoted by xti and a speed denoted by vti for i = 1, 2, ..., 5. 
That is, at time t, car1 has position xt1 and velocity vt1, car2 has position xt2 and velocity vt2, and so on. 

You are given their initial speeds and positions:
vt=0_1 = 60 km/h, vt=0_2 = 70 km/h, vt=0_3 = 80 km/h, vt=0_4 = 90 km/h, vt=0_5 = 105 km/h,
xt=0_1 = 2.05 km, xt=0_2 = 2.04 km, xt=0_3 = 2.03 km, xt=0_4 = 2.02 km, xt=0_5 = 2.0 km.

You can see that car1 is ahead on the road, followed by car2, then car3, and so on, up until we get to car5.

Keep in mind the following instructions:

1. You will be updating every car’s position and speed every second (i.e., 1/3600 h) for a total of 10s. After 1 s, you can update a car i’s position by applying:
xt=1s_i = xt=0s_i + dt * vt=0s_i where dt = 1/3600h is the chosen time step.
2. Be careful to choose units for your variables that are in sync. That is, you cannot mix seconds and hours.
3. When updating the speed of a car, keep in mind that a driver seeks to maximize their speed while maintaining at least a minimal distance dmin from the immediate front car.
4. The speed of a car at time t should be determined according to the position of the immediate front car’s position at time t.

To test your code, compute the position and speed of every car at every time step and check that they match your results. Make sure that no car is crossing one another. 
You should never get any negative speeds.

# Road class

1. You will need to specify a road’s length L and which cars are currently driving on the road.
2. You can initialize the road with an initial number of cars (you can play with that value to model roads that have a lot of traffic or a very few number of cars).
3. Every one second, with a probability of 0.5, a new car will be inserted at the beginning of the road. You can choose the initial speed of the car.
4. After a duration of dt = 1 sec, you will need to update all the cars on the road. 
If the position of the car exceeds the length of the road L, this implies that the car exited the road, and you will need to update your the cars in the Road object to account for that.
5. Develop a testing class for the Road class. We are still considering a one-lane road. You want to make sure that no cars are crossing each other.
