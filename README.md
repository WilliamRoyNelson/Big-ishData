# Big-ishData
Working with larger datasets can be hard. There's got to be a better way!


Did you get access to a 100MB+ csv file and run into this kind of problem?

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/05ecdd6f-e246-471c-b11e-91263696793c)

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/d5ebe28d-deb8-4a70-96c0-44194398eaf5)

Here's some other approaches to try

# Excel Data connection:

Start with a blank new workbook. Don't try to open the big csv file. We're going to start by going to the "Data" tab

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/1d412555-6087-4a5e-a998-0cd03db2d0dc)

Select "From Text/CSV" and open the file using the picker window.
You should end up with something like this:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/14d20e36-0a27-4f19-9b19-783862b6b92a)

Excel is pretty smart, and will likely get the settings correct automatically.

At this point it's tempting to click "Load" and get started, but if you do, you'll run into the same problem as earlier. Excel can't handle more than about a million rows.

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/7bfc605c-dc56-4ce5-a6f3-c3db5e27118d)

Instead, let's hit "Transform Data" and use some Power Query. If you've used PowerBI, this will be very familiar.

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/459624eb-a250-43d5-a518-259f9c585ff6)

There's a few ways we can go from here, but to start, I don't really want to look at every user at the same time. Let's "Group By" User:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/488015d8-c414-44b8-a595-795bc3020dd6)

Make sure to select "All Rows"

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/d5e9e868-67b5-4393-81b4-c0996b2c2f03)

Now we have everything split out by user:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/c00b5c96-001a-42b1-b74e-887cf0708867)

We can use the column headers to "sort ascending"

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/8bb37fd3-03fc-43e5-8bf5-a2120ad56ab8)


And now we can create a new query for a specific user:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/cd05445f-2440-4eb9-ae28-906ba03d9b6f)

A little easier to work with, let's use the same "sort" trick to put it in chronological order:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/638f3252-7d2a-4328-af24-fbfb90325e2e)

And we get this:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/49c28e0c-8f29-4fe3-abcb-6754639db6ad)

From here, we can load it to a spreadsheet:

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/cd5d2eef-0390-4eab-bdb0-79d20d4c86f4)

And our result is 1437 rows loaded. Much easier to work with

![image](https://github.com/WilliamRoyNelson/Big-ishData/assets/7910938/59faf21a-e6d7-45da-bc0d-9039dff3c70e)


Now, what does this mean? Why is this person rapidly marking hundreds of ballots as "EX" or "exception"? That's not clear from the data. It's a very bad idea to jump to conclusions.
Maybe they're all from a pre-sorted pile of envelopes with no signatures and they're rapidly entering them into the system for higher-level processing. Again, bad idea to jump to conclusions.

What do we do from here? I'm not great at Excel, but this should at least make it easier to work with the data.
