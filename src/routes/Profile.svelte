<!-- Profile.svelte -->
<script>
    let buttonText = "Follow";
    let description = "Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of Engineering. I write hot-takes on building a business, shipping delightful products and accelerating product and career growth.";
    let companyName = "Duggup";
    let companyLink = "https://duggup.com";
    let position = "Co-Founder and CEO";
    let firstName = "Krishna";
    let lastName = "Kiran";

    const followed = () => {
        buttonText = buttonText === "Follow" ? "Followed" : "Follow";
    }
</script>

<style>
    .profile-container {
        display: flex;
        padding: 60px 120px 60px 240px;
    }

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

    .profile-info {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .profile-info p {
        font-weight: 700;
        font-size: 20px;
        color: #4B5C6D;
        height: auto;
        margin: 0;       
    }

    .profile-description {
        font-size: 14px;
        font-style: inter;
        color: #4D4D4D;
        height: auto;
        margin: 0;
        max-width: 584px;
        height: 72px;
    }

    .profile-content {
        padding: 0px 60px;
    }

    .profile-description-container {
        display: flex;
        margin: 20px 0;
    }

    .profile-left-section {
        width: 65%;
    }

    .profile-left-section p {
        font-size: 14px;
        font-style: inter;
        color: #4D4D4D;
        height: auto;
        margin: 0;    
    }

    .profile-right-section {
        width: 35%;
        display: flex;
        flex-direction: column;
    }

    .company-info {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
    }

    .company-name {
        font-weight: 700;
        font-size: 16px;
        color: #4D4D4D;
        height: auto;
        margin: 0;
    }

    .position {
        font-size: 12px;
        color: #7A9299;
        height: auto;
        margin: 0;
        font-weight: 400;
    }

    .button-container {
        display: flex;
        justify-content: space-between;
    }

    .link-container{
        display: flex;
    }

    .link-icon {
        height: 13px;
        width: 13px;
        margin-top: 2px;
        margin-left: 5px;
        margin-right: 5px;
    }

    .link-text {
        display: flex;
        font-size: 14px;
        color: #4D4D4D;
    }

    .company-logo-container {
        display: flex;
        flex-direction: row-reverse;
    }

    .menudots{
        width: 20px;
        height: 20px;
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

<div class="profile-container">
    <div class="profile">
        <img src='images/profile/profile_pic.jpg' alt="Profile Picture"/>
        <div class="profile-info">
            <p>{firstName}</p>
            <p>{lastName}</p>
        </div>
    </div>
    <div class="profile-content">
        <div class="profile-description-container">
            <div class="profile-left-section">
                <p>{description}</p>
            </div>
            <div class="profile-right-section">
                <div class="company-logo-container">
                    <img height="36px" width="36px" src="images/profile/company_logo.jpg" alt="Logo">
                </div>
                
                <div class="company-info">
                    <p class="company-name">{companyName}</p>
                    <p class="position">{position}</p>
                </div>
            </div>
        </div>
        <div class="button-container">
            <button class="raised-button" id="follow" on:click={() => followed()}>
                {buttonText}
            </button>

            <div class="link-container">
                <a href={companyLink} target="_blank">
                    <span class="link-text">
                        My Website
                        <div class="link-icon"><img src="images/profile/link.svg" alt="Profile"/></div>
                    </span>
                </a>
                <div class="menudots">
                 <img src="images/profile/menudots.svg" alt="Profile"/>
                </div>
            </div>
        </div>
    </div>
</div>
