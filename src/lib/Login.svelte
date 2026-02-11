
<h1>Login</h1>
<form method="POST" onsubmit={loginHandler(event)}>
<label>
    Email
    <input name="email" type="email" required>
</label>
<label>
    Password
    <input name="password" type="password" required>
</label>
<button>Log in</button>
</form>

<script>
// @ts-nocheck

    /**
     * @param {{ preventDefault: () => void; target: HTMLFormElement | undefined; }} event
     */
    function loginHandler(event) {
        event.preventDefault()
        const formData = new FormData(event.target)
        const email = formData.get('email')
        const password = formData.get('password')
        console.log({ email, password })
    }
</script>

<style>
    form, button {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }
    label {
        display: flex;
        flex-direction: column;
    }
</style>