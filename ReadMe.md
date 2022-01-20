# Medium Stats

This is just a temporary quick solution of how to view your medium's lifetime stats rather than the current [medium](https://medium.com/) solution of displaying a month by month stats making it cumbersome for a writer to calculate all the stats from stories and fans received.

## Existing stats show only a month by month stat:
![Your stories stats – Medium](https://user-images.githubusercontent.com/30528167/150293368-bef09967-f587-4adb-95c5-89785ffaf22d.png)

## This script assists writers to quickly view lifetime stats:
![TotalViews](https://user-images.githubusercontent.com/30528167/150292278-afc3caa8-bb25-4abc-8486-c80209d6c325.PNG)


# Usage:

## Step 1 (Accessing Stats Page on user's Browser of Choice)
- All you need is a modern browser to start viewing your starts immediately:

### Chrome Browser Users
Open the starts page (https://medium.com/@username/stats) and type the below commands:

    Mac Users: Command + Option + J ( ⌘ + ⌥ + J)


    Linux and Windows Users: Control+Shift+J 

### Firefox Browser Users
Open the starts page (https://medium.com/@username/stats) and type the below commands:

    Mac: Command + Option + K ( ⌘ + ⌥ + K)

    Linux and Windows: Control + Shift + K

___

## Step 2 (Getting total reads):

After following the previous step, now paste below script and hit enter to view your stats:

    const totalTypes = {

        VIEWS: 2,

        READS: 3,

        FANS: 5

    };

    const getTotal = tableColumn =>

        [

            ...document.querySelectorAll(

                `td:nth-child(${tableColumn}) > span.sortableTable-number`

            )

        ]

        .map(e => parseInt(e.getAttribute("title").replace(/,/g, ""), 10))

        .reduce((a, b) => a + b, 0);

    console.log({

        totalViews: getTotal(totalTypes.VIEWS),

        totalReads: getTotal(totalTypes.READS),

        totalFans: getTotal(totalTypes.FANS)

    });