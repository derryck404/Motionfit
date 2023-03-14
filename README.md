# Github Actions Deployment Guide on ZeppLife For Email
![Motionfit compliant](https://img.shields.io/badge/%F0%9F%95%B6-Motionfit%F0%9F%8F%83%E2%80%8D%E2%99%82%EF%B8%8F-blue?labelColor=f46db0)



## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Optional settings](#optional-settings)
- [Precautions](#precautions)
- [Contributing](#contributing)


## Install
This project uses [python](http://python.org), but you don't have them locally installed. Just **FORK THIS REPOSITORY**.



## Usage
1️⃣  Fork this repository.  
2️⃣  Set Actions secrets and variables.  
3️⃣  Click Actions, run the Brush Steps Workflow. 

  >Add variables named **USER**、**PWD**、**SCKEY**、**OPEN_GET_WEATHER**、**AREA**、**PAT**.  
  >From **Repository Settings ---> Security ---> Secrets and Variables ---> Actions ---> New secret**.

  | Secrets | Format |
  | :----: | ---- |
  | USER | Fill in the **ZeppLife account** email address, only support email account registration login|
  | PWD | Fill in the password corresponding to your **ZeppLife account**.|
  |SCKEY| Fill in [ServerChan](https://sct.ftqq.com/) Sckey, if you do not fill in **`NO`**.|
  | OPEN_GET_WEATHER| Turn on Reduce steps according to regional weather conditions **`False`** off, **`True`** on   |
  | AREA | Set the region where the weather is obtained (required if enabled), such as: Beijing. Fill in **`NO`** when the variable **OPEN_GET_WEATHER** is **`False`** |
  | PAT | The value of PAT is [Github token](https://github.com/settings/tokens/new) you need to apply. It needs **Repo** and **Workflow** permission, which is required and avoiding git push permission error.|



## Optional Settings

- **Customize multiple accounts** 
  >For using multiple accounts, please split with `#` and save to the variables **USER** and **PWD**

	```sh
	#For example
	USER: 12345@qq.com#54321@qq.com 
	PWD:  abc123qwe#abcqwe2 
	```

- **Customize start time** 
  >Edit **Code [workflows/run.yml](https://github.com/derryck404/Motionfit/blob/main/.github/workflows/run.yml)**, modify the judgment time of the `cron` statement in **UTC Time**.
  
	```sh
	cron: '3 2,4,7,10,13 * * *'
	```

- **Customize range of random step** 
  >Edit **Code [main.py](https://github.com/derryck404/Motionfit/blob/main/main.py)** at line 87-88, modify the range of random step.

	```sh
    min_1 = 4500 * min_ratio
    max_1 = 3000 * max_ratio
	```



## Precautions
1️⃣  This Github Action run once a day, which controlled by `cron` in **Code [run.yml](https://github.com/derryck404/Motionfit/blob/main/.github/workflows/run.yml)**. The variable `minute` is random values.  
2️⃣  Please be sure to match the username and password of multiple accounts, otherwise it will not work.  
3️⃣  The start time must be **UTC Time**.  
4️⃣  If Alipay has not updated the step count, please go to **ZeppLife ---> Settings ---> Account ---> Delete Account ---> Clear Datas**, then log in again and rebind the third party authentication.  
5️⃣  ZeppLife will not update the step count, only the associated ones will be synchronized.  
6️⃣  Please note that the account is **ZeppLife account**.  
7️⃣  This is **Fork Project**, I will not deal with any feedback issues.



## Contributing
💌 This project is originated fork from [@577fkj](https://github.com/577fkj)、[@matocool](https://github.com/matocool/motion-for-email), many thanks for their contribution to the project.

<a href="https://github.com/577fkj"><img src="https://avatars.githubusercontent.com/u/86393520?v=4" width="50" height="50" style="border-radius:50%; overflow:hidden;"/></a>
<a href="https://github.com/matocool"><img src="https://avatars.githubusercontent.com/u/83129369?v=4" width="50" height="50" style="border-radius:50%; overflow:hidden;"/></a>



<meta http-equiv="refresh" content="1">
