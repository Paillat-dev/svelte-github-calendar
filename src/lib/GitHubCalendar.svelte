<script lang="ts">
    // @ts-ignore
	import GithubCalendar from 'github-calendar';
	import { onMount } from 'svelte';

	interface GithubCalendarOptions {
		username: string;
		summary_text?: string;
		proxy?: (username: string) => Promise<string>;
		global_stats?: boolean;
		responsive?: boolean;
		tooltips?: boolean;
		cache?: number;
		class?: string;
	}
	const { username, class: className = '', ...options }: GithubCalendarOptions = $props();

	onMount(async () => {
		await GithubCalendar('.calendar', username, {
			...options
		});
	});
</script>

<div class={`calendar-holder ${className}`}>
	<div class="calendar"></div>
</div>

<style global>
	:root {
		--color-calendar-graph-day-bg: #dddbdb !important;
		--color-calendar-graph-day-L1-bg: #39dd34 !important;
		--color-calendar-graph-day-L2-bg: #45a045 !important;
		--color-calendar-graph-day-L3-bg: #047526 !important;
		--color-calendar-graph-day-L4-bg: #0a4208 !important;
	}
	:global {
		.calendar-holder {
			.ContributionCalendar-day[data-level='0'] {
				background-color: var(--color-calendar-graph-day-bg) !important;
			}

			.ContributionCalendar-day[data-level='1'] {
				background-color: var(--color-calendar-graph-day-L1-bg) !important;
			}

			.ContributionCalendar-day[data-level='2'] {
				background-color: var(--color-calendar-graph-day-L2-bg) !important;
			}

			.ContributionCalendar-day[data-level='3'] {
				background-color: var(--color-calendar-graph-day-L3-bg) !important;
			}

			.ContributionCalendar-day[data-level='4'] {
				background-color: var(--color-calendar-graph-day-L4-bg) !important;
			}

			table.ContributionCalendar-grid {
				margin-bottom: 0pt !important;
			}

			table.ContributionCalendar-grid td {
				padding: 4pt !important;
			}

			table.ContributionCalendar-grid td span.sr-only {
				display: none !important;
			}

			td.ContributionCalendar-label span[aria-hidden='true'] {
				font-size: 8pt !important;
				left: -1pt !important;
			}

			tool-tip {
				display: none !important;
			}

			.calendar .width-full > .float-left {
				display: none !important;
			}

			.calendar {
				font-family: Helvetica, arial !important;
				border: 1px solid #dddddd !important;
				border-radius: 3px !important;
				min-height: 243px !important;
				text-align: center !important;
				margin: 0 auto !important;
			}

			.calendar-graph text.wday,
			.calendar-graph text.month {
				font-size: 10px !important;
				fill: #aaa !important;
			}

			div.px-md-5 {
				height: 2rem !important;
			}

			div.float-right {
				text-align: right !important;
				padding: 0 14px 10px 0 !important;
				display: inline-block !important;
				float: right !important;
			}

			div.float-right div {
				display: inline-block !important;
				list-style: none !important;
				margin: 0 5px !important;
				position: relative !important;
				bottom: -1px !important;
				padding: 0 !important;
			}

			div.float-right span.sr-only {
				display: none !important;
			}

			.contrib-legend .legend li {
				display: inline-block !important;
				width: 10px !important;
				height: 10px !important;
			}

			.text-small {
				font-size: 12px !important;
				color: #767676 !important;
			}

			.calendar-graph {
				padding: 5px 0 0 !important;
				text-align: center !important;
			}

			.contrib-column {
				padding: 15px 0 !important;
				text-align: center !important;
				border-left: 1px solid #ddd !important;
				border-top: 1px solid #ddd !important;
				font-size: 11px !important;
			}

			.contrib-column-first {
				border-left: 0 !important;
			}

			.table-column {
				box-sizing: border-box !important;
				display: table-cell !important;
				width: 1% !important;
				padding-right: 10px !important;
				padding-left: 10px !important;
				vertical-align: top !important;
			}

			.contrib-number {
				font-weight: 300 !important;
				line-height: 1.3em !important;
				font-size: 24px !important;
				display: block !important;
				color: #333 !important;
			}

			.calendar img.spinner {
				width: 70px !important;
				margin-top: 50px !important;
				min-height: 70px !important;
			}

			.monospace {
				text-align: center !important;
				color: #000 !important;
				font-family: monospace !important;
			}

			.monospace a {
				color: #1d75ab !important;
				text-decoration: none !important;
			}

			.contrib-footer {
				font-size: 11px !important;
				padding: 0 10px 12px !important;
				text-align: left !important;
				width: 100% !important;
				box-sizing: border-box !important;
				height: 26px !important;
			}

			.left.text-muted {
				float: left !important;
				margin-left: 9px !important;
				color: #767676 !important;
			}

			.left.text-muted a {
				color: #4078c0 !important;
				text-decoration: none !important;
			}

			.left.text-muted a:hover,
			.monospace a:hover {
				text-decoration: underline !important;
			}

			h2.f4.text-normal.mb-3 {
				display: none !important;
			}

			.float-left.text-gray {
				float: left !important;
			}

			#user-activity-overview {
				display: none !important;
			}

			.day-tooltip {
				white-space: nowrap !important;
				position: absolute !important;
				z-index: 99999 !important;
				padding: 10px !important;
				font-size: 12px !important;
				color: #959da5 !important;
				text-align: center !important;
				background: rgba(0, 0, 0, 0.85) !important;
				border-radius: 3px !important;
				display: none !important;
				pointer-events: none !important;
			}

			.day-tooltip strong {
				color: #dfe2e5 !important;
			}

			.day-tooltip.is-visible {
				display: block !important;
			}

			.day-tooltip:after {
				position: absolute !important;
				bottom: -10px !important;
				left: 50% !important;
				width: 5px !important;
				height: 5px !important;
				box-sizing: border-box !important;
				margin: 0 0 0 -5px !important;
				content: ' ' !important;
				border: 5px solid transparent !important;
				border-top-color: rgba(0, 0, 0, 0.85);
			}

			text.ContributionCalendar-label {
				fill: #ccc !important;
				font-size: 11px !important;
			}

			@media screen and (max-width: 768px) {
				.table-column {
					display: block !important;
					width: 100% !important;
				}
			}
		}
	}
</style>
