README

Step-by-Step Breakdown

Sources

I used sources like Javatpoint.com, GeeksforGeeks.org, Stackoverflow and other GitHub projects as inspiration. These references provided  insights for implementing the rotation logic.

1. Initial Setup and Clock Refresh

The setInterval function ensures the clock updates every second:

setInterval(refreshClock, 1000);

Before the periodic updates, the clock is initialized by calling:

refreshClock();

2. Extracting Time Data

The refreshClock function retrieves the current hour, minute, and second using the JavaScript Date object:

const currentTime = new Date();

getHours(): Retrieves the current hour.

getMinutes(): Retrieves the current minute.

getSeconds(): Retrieves the current second.

3. Calculating Hand Rotations

To display the correct time, the script calculates the rotation angles for the hour, minute, and second hands:

Hour Hand Rotation:

const hrRotation = ((hrs % 12) + mins / 60) * 30;
This calculation ensures that the hour hand smoothly progresses as minutes pass.

Minute Hand Rotation:

const minRotation = (mins + secs / 60) * 6;
This calculation makes the minute hand move smoothly as seconds pass.

Second Hand Rotation:

const secRotation = secs * 6;
This ensures that the second hand moves precisely every second.

4. Updating the Clock Display

After computing the rotation angles, the script identifies the clock hands and applies the calculated transformations:

const hrHand = document.querySelector('.hour-hand');

const mnHand = document.querySelector('.min-hand');

const scHand = document.querySelector('.second-hand');

The hands are rotated using CSS transforms:

hrHand.style.transform = translate(-50%, 0) rotate(${hrRotation}deg);

mnHand.style.transform = translate(-50%, 0) rotate(${minRotation}deg);

scHand.style.transform = translate(-50%, 0) rotate(${secRotation}deg);
