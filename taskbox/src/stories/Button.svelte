<script>
    import './button.css';

    /**
     * Is this the principal call to action on the page?
     */
    export let primary = false;

    /**
     * What background color to use
     */
    export let backgroundColor;
    /**
     * How large should the button be?
     */
    export let size = 'medium';
    export let label = '';


    let mode = primary ? 'storybook-button--primary' : 'storybook-button--secondary';

    let style = backgroundColor ? `background-color: ${backgroundColor}` : '';


    export let toggleView
</script>

<button
        type="button"
        class={['storybook-button', `storybook-button--${size}`, mode].join(' ')}
        {style}
        on:click={toggleView} on:keydown={toggleView}>  {label}
</button>

