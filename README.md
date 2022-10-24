# Render Prefect Agent
This is a simple repo for setting up a Prefect 2 agent as a background worker on render.com. I will take no credit for this as Yaron Levi from the Prefect slack community 
supported me and gave me everything that is here. So all I am doing here is gathering it in oneplace and allow others to benefit from his knowledge.

# 1.
Clone this repo or create your own with 2 files.

requirements.txt - for me it needed these pip packages

![image](https://user-images.githubusercontent.com/6391422/197524239-ae9bb21c-65c2-49f9-8f94-36366432b387.png)

build.sh which runs 
pip install -r requirements.txt

![image](https://user-images.githubusercontent.com/6391422/197524473-d3b2e7e4-3d5b-46ed-8991-ccc0ba82b87e.png)

# 2
Create a background worker on render.com and point it to a github repo.
Give it a name

![image](https://user-images.githubusercontent.com/6391422/197524953-2476501f-dfb7-4db5-b852-f34c142a74a2.png)

select a branch

![image](https://user-images.githubusercontent.com/6391422/197525332-3451b1e4-844e-4b4b-a8d3-0f5903f7e6f6.png)

add the build settings and startup command: **prefect agent start --work-queue "default"**, this starts the agent and sets the work-queue name to "default"

![image](https://user-images.githubusercontent.com/6391422/197525553-2c1c1b7a-bb2e-4569-918a-e8d79480c744.png)

Add your Prefect API Key and api url as environmental variables under advanced

![image](https://user-images.githubusercontent.com/6391422/197525926-8ae5b358-3a01-4f20-bc3f-e26ec2cdfb37.png)

And deploy you should now see a deployment process starting which ends with a starting agent. 
