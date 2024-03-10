<!-- Profile.svelte -->
<script>
    let buttonText = "Follow";

    const followed = () => {
        buttonText = buttonText === "Follow" ? "Followed" : "Follow";
    }
</script>

<style>
    .profile {
        display: flex;
        flex-direction: column;
    }

    .profile img {
        width: 120px;
        height: 120px;
        border-radius: 50%;
        border: 5px solid #EAEFF5;
    }

    .profile p {
        font-size: 14px;
        font-style: inter;
        color: #4D4D4D;
        margin: 0;
        max-width: 584px;
        height: 72px;
    }

    .raised-button {
        box-shadow: 0px 4px 0px 0px #4D4D4D;
        background-color: white;
        color: #4D4D4D;
        border: 0.5px solid #4D4D4D;
        margin-top: 4px;
        width: 120px;
    }
</style>

<div style="display: flex; padding: 60px 120px 60px 240px;">
    <div class="profile">
        <img src='https://media.licdn.com/dms/image/D4E03AQF-fLP5TtdtOQ/profile-displayphoto-shrink_400_400/0/1677089436637?e=1715212800&v=beta&t=J9-kSXKFOUgtVi6XPQhaWVHz74by4_pPnILLu6S3S6Y' alt="Profile Picture"/>
        <div style="display: flex; flex-direction: column; justify-content: center; align-items: center;">
            <p style="font-weight: 600; font-size: 18px; color: #4D4D4D; height: auto;">Krishna</p>
            <p style="font-weight: 600; font-size: 18px; color: #4D4D4D; height: auto;">&nbsp;Kiran</p>
        </div>
    </div>
    <div style="padding: 0px 60px;">
        <div style="display: flex; margin: 20px 0">
            <div style="width: 65%; ">
                <p style="font-size: 14px; font-style: inter; color: #4D4D4D; height: auto; margin: 0;">
                    Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of Engineering. I write hot-takes on building a business, shipping delightful products and accelerating product and career growth.
                </p>
            </div>
            <div style="width: 35%; display: flex; flex-direction: column;">
                <div style = "display: flex; flex-direction: row-reverse">
                    <img height="36px" width="36px" src="https://media.licdn.com/dms/image/D560BAQFHRBPTiTkqnA/company-logo_100_100/0/1687508146558/duggup_logo?e=1717632000&v=beta&t=xSqWU_IIJJTtXYzh2q7PTIulC5u7gsDwdq36CcPnU4U" alt="Logo">
                </div>
                
                <div style = "display: flex; flex-direction: column;  align-items: flex-end">
                    <p style="font-weight: 700; font-size: 16px; color: #4D4D4D; height: auto; margin: 0; ">Duggup</p>
                    <p style="font-size: 12px; color: #7A9299; height: auto; margin: 0;">Co-Founder and CEO</p>
                </div>
               
            </div>
        </div>
        <div style="display: flex; justify-content: space-between;">
            <button class="raised-button" id="follow" on:click={() => followed()}>
                {buttonText}
            </button>

            <div style="display: flex; ">
                        <a >
                <span style="font-size: 14px; color: #4D4D4D;">
                    My Website
                </span>
            </a>
        <div style="height: 13px; width: 13px; margin-top:2px;margin-left: 5px">
            <img src="images/profile/link.svg" alt="Profile"/>
            </div>
            </div>
        </div>
    </div>
</div>
