# bookmarklets
A list of bookmarklets

<a id="bookmarklet-a" class="bookmarklet" href="javascript:(function()%7Bjavascript%3A(function()%20%7B%0A%20%20%20%20function%20findAndClickButtonByText(text)%20%7B%0A%20%20%20%20%20%20%20%20const%20buttons%20%3D%20document.querySelectorAll('button')%3B%0A%20%20%20%20%20%20%20%20for%20(const%20button%20of%20buttons)%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20(button.textContent.includes(text))%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20button.click()%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20true%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20return%20false%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20const%20keywords%20%3D%20%5B'Unfollow'%2C%20'Joined'%5D%3B%0A%20%20%20%20for%20(const%20keyword%20of%20keywords)%20%7B%0A%20%20%20%20%20%20%20%20if%20(findAndClickButtonByText(keyword))%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20break%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D)()%3B%7D)()%3B">Reddit Unfollow/Leave </a>

javascript:(function() {
    function findAndClickButtonByText(text) {
        const buttons = document.querySelectorAll('button');
        for (const button of buttons) {
            if (button.textContent.includes(text)) {
                button.click();
                return true;
            }
        }
        return false;
    }

    const keywords = ['Unfollow', 'Joined'];
    for (const keyword of keywords) {
        if (findAndClickButtonByText(keyword)) {
            break;
        }
    }
})();
