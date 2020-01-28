<script>
    export let loggedIn = false;

    function handleClick () {
        loggedIn = !loggedIn;
    }
</script>

<div class="app-bar">
    <div>
        <a href="/" class="logo">FLAKE</a>
    </div>
    <div class="app-bar-right">
        {#if loggedIn}
            <div>
                <ul>
                    <li><a href="/dashboard">Dashboard</a></li>
                    <li><a href="/workspace">Workspace</a></li>
                    <li><a href="/search">Search</a></li>
                </ul>
            </div>
        {/if}
        <div>
            <button on:click={handleClick}>{loggedIn ? 'Log Out' : 'Login'}</button>
        </div>
    </div>
</div>

<style>
    a {
        color: #ff3e00;
    }
    ul {
        width: 400px;
        display: flex;
        justify-content: space-around;
        list-style-type: none;
    }
    .app-bar {
        height: 50px;
        display: flex;
        justify-content: space-between;
    }
    .app-bar-right {
        display: flex;
    }
	.logo {
		color: #ff3e00;
        text-decoration: none;
		text-transform: uppercase;
        font-size: 24px;
		font-weight: 400;
	}
</style>