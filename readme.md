# Yarn Workspace Example

This project showcases the potential usage of yarn workspace to create a micro frontend architecture. Our current use-case requires us to build 3 different Web-apps with a common component library.

Web applications:

- Agent application: Web application to be used by insurance agents to fill applcation and KYC details of end customers
- Underwriter: Web application to be used by underwriters (Niravana's Employees) to evaluate customers and propose final quotations
- Safety: Web application to be used by both insurance agents and end customers (probably). Will use CAB reports from DoT to gain quick insights on customers driving patterns and historical data.

# Arctitecture

```
	-niravana-client
		-packages
			-agent
			-safety
			-ui-kit
		-package.json
```

## Agent App

Agent App is bootstraped using `create-react-app`.

Use `yarn start` to start local server

## Safety App

Safety App is bootstraped using `vitejs`

Use `yarn dev` to start local server

## ui-kit

Ui-kit is our component library which will provide basic building blocks for other applications. We can add ui-kit as a dependency in other packages.

Ui-kit is bootstraped using `create-react-library`.

### Usage of ui-kit

```
	import {Button} from '@niravana-client/ui-kit';
	import {HiCalendar} from 'react-icons/hi`;

	export default function App() {
		return (
			<Button startIcon={<HiCalendar />}>Click Me!!!</Button>
		)
	}
```
