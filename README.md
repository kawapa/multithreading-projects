# Description
Assignments from "Multithreading in C++" course from Coders School (https://coders.school/):

1. [Multithreaded `std::accumulate`](#1-multithreaded-stdaccumulate)
2. [Multithreaded `std::count_if`](#2-multithreaded-stdcount_if)
3. [Dining philosophers](#3-dining-philosophers)
4. [Ping-pong](#4-ping-pong)
5. [Multithreaded `std::accumulate` using `std::assync`](#5-multithreaded-stdaccumulate-using-stdassync)
6. [OpenCV - image processing](#6-opencv---image-processing)

## 1. Multithreaded `std::accumulate`

[Source code](src/1-accumulate/main.cpp)<br>
**Description**<br>
Write an multithreaded version of the STL algorithm `std::accumulate`. Other requirements:
- [x] On empty - return init
- [x] Calculate number of threads using formula `hardware_threads = hardware_concurrency() 0 ? hardware_concurrency() : 2`
- [x] Divide on blocks according to the number of threads
- [x] Create vector of results
- [x] Run every thread in parallel
- [x] Put results in vector element passed by reference (threads cannot return value)
- [x] Join threads
- [x] Accumulate results from the result vector
- [x] Test on 1M elements and compare with standard std::accumulate
- [x] Templatize algorithm on Iterator (depends on container) and type T sually int, double)

## 2. Multithreaded `std::count_if`

[Source code](src/2-count_if/main.cpp)<br>
**Description**<br>
Write an multithreaded version of the STL algorithm `std::count_if`. Other requirements:
- [x] Measure the duration of the application 
- [x] Write tests that confirms it gives the same results as STL `std::count_if`
- [x] Compare your solution with STL `std::count_if` with `std::execution::par` policy (C++17)

## 3. Dining philosophers

[Source code](src/3-dining_philosophers/main.cpp)<br>
**Description**<br>
Implement the wide-known problem of dining philosophers ([Wiki](https://en.wikipedia.org/wiki/Dining_philosophers_problem)) using threads and mutexs. Other requirements:
- [x] Every philosopher is run by a separate thread
- [x] Every fork is protected by a separate mutex
- [x] Visualize what is happening in the termial 
- [x] Avoid deadlocks
- [x] Play with the numbers of philosophers (and forks) and draw conclusions
- [ ] Implement anti-starvation mechanism ([Wiki](https://en.wikipedia.org/wiki/Starvation_(computer_science)))

## 4. Ping-pong

[Source code](src/4-ping_pong/main.cpp)<br>
**Description**<br>
Implement the ping-pong game in the terminal. Requirements:
- [x] One thread outputs `Ping` and a integer
- [x] The other thread outputs `Pong` and a integer
- [x] Threads use `std::cout` alternately
- [x] The game must always start with `Ping` and end with `Pong`
- [x] Application ends after given number of hits or after given period of time has elapsed (pass those as paramaters, for example `./a.out 10 5`)

## 5. Multithreaded `std::accumulate` using `std::assync`

[Source code](src/5-accumulate_assync/main.cpp)<br>
**Description**<br>
Implement the analogous application as explained in exercise 1 but use `std::assync`.

## 6. OpenCV - image processing

[Source code](https://github.com/kawapa/multithreading-projects) - Template Matching<br>
[Source code](https://github.com/kawapa/multithreading-projects) - Morph Line Detection<br>
**Description**<br>
Using the library OpenCV, implement the multithreaded versions of algorithms:
- [ ] Template Matching
    * Every thread looks for different
    * Display the area(s) of the greatest match
- [ ] Morph Line Detection
    * Every thread looks for a line at different angle
    * Create appropriate masks
    * Display the lines on the original pictures (use different colours for different angles)