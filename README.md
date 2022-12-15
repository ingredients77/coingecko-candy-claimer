# coingecko-candy-claimer

This script auto claims coingecko candy according to the time interval you set.

# Setup

1. Login to your **Coingecko.com** account and make sure **remember me** is checked while doing so.

![image](https://user-images.githubusercontent.com/120642025/207834913-9b278b43-f132-4423-82ae-658b854ff7d7.png)

2. After logging in, open the **developer console** by pressing **F12** on your keyboard.

3. Click the network tab and refresh the page by pressing **F5** or by using your browser's refresh button. Make sure you don't close the developer console. Firefox was used in this demonstration. Chrome and other browsers can be used as well.

![image](https://user-images.githubusercontent.com/120642025/207835663-ca67fc49-0c46-484c-b54a-eb8ee7e5713e.png)

4. After the page refreshes, scroll up the **network tab** and click the **GET** request to the domain **wwww.coingecko.com** for file **/**.

![image](https://user-images.githubusercontent.com/120642025/207837030-74962a8f-30eb-4cad-b017-e172443ae180.png)

5. A new section will be opened on the right with the **headers** tab already selected.

6. Scroll down and look for the **cookie** under the **request headers tab**.

7. Right click the **cookies** and click **copy value**.
![image](https://user-images.githubusercontent.com/120642025/207839888-10191ef4-ac59-4c80-85d0-525e7fdaf956.png)

8. Paste the copied **cookies** into the **cookies.txt** file and save it. **Make sure you keep your cookies safe and secure. Any one with the cookies can access your account.**

9. **Make sure you don't sign out of your coingecko account or it will render the cookies invalid. Close the window instead.**

# Running the script

1. Clone the repo to your VPS with `git clone https://github.com/ingredients77/coingecko-candy-claimer`.

2. Cd into coingecko-candy-claimer with `cd coingecko-candy-claimer` and edit the cookies.txt file by typing `nano cookies.txt`

3. Paste the cookies and save it by pressing Ctrl + X, press Y and then Enter.

4. Install the requirements using `pip3 install -r requirements.txt` or `pip install -r requirements.txt`

5. Create a new **tmux** window with `tmux new-session -s coingecko-candy`. This will create a new tmux window that will allow the script to run in the background and prevent the script from getting interupted.

6. Now type `watch -n 22320 python3 geckocandy.py`. This will run the script every 6 hours and claim your candy automatically every 6 hours. You can adjust the time to your liking.

![image](https://user-images.githubusercontent.com/120642025/207847392-c627348c-9d0d-46ae-bf47-e072f0f85ac1.png)


7. Press **Ctrl + B** and then *D* to detach from the tmux window. You can always go back to the window by typing `tmux attach-session -s coingecko-candy`.

8. Alternative to step 5 and 6, you can use crontab to schedule the interval you want the script to run.

