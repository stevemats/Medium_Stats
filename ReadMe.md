# Medium Stats

This is just a solution to view your medium's lifetime stats rather than the current medium solution of displaying just a month by month stats making it cubersome to calculate all the stats from stories and fans received.
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