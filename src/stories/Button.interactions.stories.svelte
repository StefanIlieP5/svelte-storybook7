<script lang="ts">
	import { Meta, Story, Template } from '@storybook/addon-svelte-csf';
	import Button from './Button.svelte.js';
	import { within, waitFor, userEvent } from '@storybook/testing-library';

	import { expect } from '@storybook/jest';
</script>

<Meta
	title="Example/Button"
	component={Button}
	parameters={{
		docs: {}
	}}
	argTypes={{
		backgroundColor: { control: 'color' },
		size: {
			control: { type: 'select' },
			options: ['small', 'medium', 'large']
		}
	}}
/>

<Template let:args>
	<Button {...args} />
</Template>

<Story
	name="Primary"
	args={{
		primary: true,
		label: 'Button'
	}}
	play={({ canvasElement }) => {
		userEvent.tab({ focusTrap: canvasElement });
	}}
/>
