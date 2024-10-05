# CHEVRON-PORTFOLIO-DASHBOARD(SAMPLE DATA)


## Overview

The **Chevron Portfolio Dashboard** is a web-based interactive dashboard designed to provide insights into Chevron’s financial performance across multiple years. The dashboard displays key metrics like revenue, operating costs, net profit, capital expenditures, production volume, and market capitalization. It also includes features like dark mode, dynamic charts, and a report generator.

## Features

- **Dark Mode**: Toggle between light and dark modes for better readability.
- **Dynamic Charts**: Interactive `AreaChart` and `BarChart` visualizations powered by `Recharts`.
- **Key Performance Metrics**: Cards showing year-over-year financial growth with visual indicators (up/down arrows).
- **Financial Report Generation**: Automatically generate a summary of Chevron’s financial performance and receive recommendations for strategic improvements.

## Technologies Used

- **React**: For building the user interface.
- **Next.js**: For server-side rendering and routing.
- **Recharts**: For creating interactive charts and data visualizations.
- **Lucide Icons**: For modern and scalable icons.
- **Tailwind CSS**: For custom styling and responsive design.

---

## Getting Started

Follow these instructions to set up and run the project on your local machine for development and testing purposes.

### Prerequisites

Make sure you have the following installed:

- **Node.js** (>= 14.0)
- **NPM** or **Yarn** (for dependency management)

### Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/yourusername/chevron-dashboard.git
    cd chevron-dashboard
    ```

2. **Install the dependencies**:

    ```bash
    npm install
    ```

    or if you use Yarn:

    ```bash
    yarn install
    ```

3. **Start the development server**:

    ```bash
    npm run dev
    ```

    or with Yarn:

    ```bash
    yarn dev
    ```

4. **Open the dashboard**:

    Navigate to `http://localhost:3000` in your browser to view the dashboard.

---

## Usage

### Dashboard Features

- **Switch between light and dark modes**: Use the toggle switch on the top right corner to switch between themes.
- **Interactive charts**: Hover over the charts to see data points and click on the bars to log specific year data to the console.
- **Generate Financial Report**: Click on the "Generate Report" button to view an auto-generated performance report with recommendations for Chevron’s portfolio.

### Data Visualization

The dashboard displays data for the following financial years:
- 2020
- 2021
- 2022
- 2023

Metrics included:
- **Revenue**
- **Operating Costs**
- **Net Profit**
- **Capital Expenditures**
- **Production Volume**
- **Share Price**
- **Dividend Yield**
- **Market Capitalization**

### Sample Code Snippets

**Revenue vs Operating Costs Chart**:

```jsx
<ResponsiveContainer width="100%" height={300}>
  <AreaChart 
    data={data}
    onMouseEnter={handleMouseEnter}
    onClick={handleClick}
  >
    <defs>
      <linearGradient id="colorRevenue" x1="0" y1="0" x2="0" y2="1">
        <stop offset="5%" stopColor="#0066b2" stopOpacity={0.8}/>
        <stop offset="95%" stopColor="#0066b2" stopOpacity={0}/>
      </linearGradient>
      <linearGradient id="colorOperatingCosts" x1="0" y1="0" x2="0" y2="1">
        <stop offset="5%" stopColor="#82ca9d" stopOpacity={0.8}/>
        <stop offset="95%" stopColor="#82ca9d" stopOpacity={0}/>
      </linearGradient>
    </defs>
    <CartesianGrid strokeDasharray="3 3" stroke={darkMode ? "#444" : "#ccc"} />
    <XAxis dataKey="year" stroke={darkMode ? "#888" : "#666"} />
    <YAxis stroke={darkMode ? "#888" : "#666"} />
    <Tooltip contentStyle={{ backgroundColor: darkMode ? '#333' : '#fff', border: 'none' }} />
    <Legend />
    <Area 
      type={curveMonotoneX}
      dataKey="revenue" 
      stroke="#0066b2" 
      fillOpacity={1} 
      fill="url(#colorRevenue)" 
      animationDuration={1000}
      isAnimationActive={true}
    />
    <Area 
      type={curveMonotoneX}
      dataKey="operatingCosts" 
      stroke="#82ca9d" 
      fillOpacity={1} 
      fill="url(#colorOperatingCosts)" 
      animationDuration={1000}
      isAnimationActive={true}
    />
  </AreaChart>
</ResponsiveContainer>
