calculations
============

#include <stdio.h>
#include <math.h>
#include <grx20.h>
#define pressure_at_sea_level 101325, gravitational_constant 6.67384*pow(10, -11, radius_of_earth 6378100, mass_of_earth 5.9726*pow(10, 24), boltzman_constant 1.3806488 * pow(10, -23), gas_constant_R 8.31 4462175, molar_mass_of_air 0.02897

float velocity, altitude, gravity, acceleration, mass, density, thrust, drag_coefficient, area_which_experiences_drag, air_temp, dt, fuel_rate, drag;
int current.row;



main () {
     drag_coefficient = 1; /*made up*/
     area_which_experiences_drag = 1; /*made up*/
     fuel_rate = 1; /*need to look this up*/
     current.row = 0;
     thrust = 1; /*made up*/
     air_temp = 1; /*made up*/
     velocity = 0;
     altitude = 0;
     mass = 1; /*this is madeup*/
     dt = 1; /*let them chose this in proper one*/
     gravity = gravity = (gravitational_constant * mass_of_earth) / (pow(radius_of_earth + altitude,2));
     mechanics();
     }

void mechanics (current.row, velocity, altitude, gravity, mass, density, drag, acceleration) {
     while (current.row > 1001) {
           density = calc_density(); /*wrong*/
           drag = calc_drag();
           acceleration = calc_acceleration();
           velocity = calc_velocity();
           altitude = calc_altitude();
           gravity = calc_gravity();
           mass = calc_mass();
           current.row = current.row + 1;
           }
           
float calc_velocity(velocity, acceleration, dt) {
     velocity = velocity + acceleration * dt;
     return velocity;
     }

float calc_altitude(altitude, velocity, dt) {
      altitude = altitude + velocity * dt;
      return altitude;
      }

float calc_gravity(gravity, altitude) {
      gravity = (gravitational_constant * mass_of_earth) / (pow(radius_of_earth + altitude,2));
      return gravity;
      }

float calc_mass(mass, fuel_rate, dt) {
      mass = mass - fuel_rate * dt;
      return mass;
      }

float calc_density(density, mass, gravity, altitude, air_temp) {
      density = ((pressure_at_sea_level * molar_mass_of_air)/ (air_temp * gas_constant_R)) * pow(exp,(-1 * mass * gravity * altitude) / (boltzman_constant * air_temp)) ; /*wrong*/
      return density;
      }

float calc_drag(drag, drag_coefficient, density, area_which_experiences_drag, velocity) {
      drag = (drag_coefficient * density * pow(velocity, 2) * area_which_experiences_drag) / 2;
      return drag;
      }

float calc_acceleration(acceleration, thrust, drag, mass, gravity) {
      acceleration = (thrust - drag) / mass - gravity;
      return acceleration;
      }
