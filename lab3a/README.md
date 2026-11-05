# Lab 3A: Produce 
A small Express API that returns a list of produce (fruits and vegetable) as JSON, and a React component that fetches and displays it.
## Run the API (terminal 1)
    cd server
    npm install
    npm start          # http://localhost:3001/api/items

## Run the React app (terminal 2)
    cd client
    npm install
    npm run dev        # open the URL Vite prints, usually http://localhost:5173

<!-- Start the API first. The React app's /api requests are forwarded to Express, so if the API isn't running yet, the first load shows the error state. -->

## Short note

The component is always in one of three states. Loading shows "Loading" while the request is in flight, error shows an alert with the message if anything fails, and success renders the list of produce names. Checking response.ok is necessary because fetch only rejects when no response arrives at all; a 404 or 500 is still a response, so without the check the code would treat the error JSON as real data and break instead of showing the error state.