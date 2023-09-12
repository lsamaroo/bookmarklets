# bookmarklets
A list of bookmarklets

Leave ALL reddit group/users

Add the code below to one of these online bookmarklet maker e.g. https://mrcoles.com/bookmarklet/  and drag and drop your new bookmarklet to the bookmark bar.  
Go to reddit, find the page which lists all your users and communites on the left and click on the bookmarklet. 

javascript:(async function() {
    function findAndClickButtonByText(text) {
        const buttons = document.querySelectorAll('button, span');
        for (const button of buttons) {
            if (button.textContent.includes(text)) {
                button.click();
                return true;
            }
        }
        return false;
    }

    async function clickMenuItemsAndWait() {
        const menuItems = document.querySelectorAll('a[role="menuitem"]');
        for (const menuItem of menuItems) {
            menuItem.click();
            await new Promise(resolve => setTimeout(resolve, 3000)); // Wait for 3 seconds
            findAndClickButtonByText('Unfollow') || findAndClickButtonByText('Leave');
        }
    }

    await clickMenuItemsAndWait();
})();
