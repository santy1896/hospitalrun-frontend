## HospitalRun Frontend

1. Check out the HospitalRun General Contributing Guide for how to:
1. Browse Issues
2. Get Assigned an Issue
3. Fork the Repository and Create a Branch
4. Commit Changes
5. Submit a Pull Request

2. After creating a local fork (step 3 above), follow these steps to configure CouchDB
CouchDB is the server side database which data from the frontend will sync from and to. CouchDB is required to login to HospitalRun. You could install and run CouchDB in any way you wish. For convienence, we have added a docker compose file in the root of this project to launch CouchDB. Below are the steps:
1. Start Docker. Install it if you don't have it yet.
2. Install Docker Compose if you don't have it yet.
3. In the root directory run ./couchdb/couchdb-init.bat on Windows or ./couchdb/couchdb-init.sh on UNIX like systems.
This should launch a new CouchDB instance on http://localhost:5984, create system database, configure CouchDB as Single Node, enable CORS, create hospitalrun database, create a default admin with a username of admin and password of 'password', create a sample user with a username of username and password of 'password' to use new login page #2137.
Go to http://localhost:5984/_utils in your browser to view Fauxton and perform administrative tasks.
Cleanup To delete the development database, go to the root of the project and run ./couchdb/couchdb-cleanup.bat on Windows or ./couchdb/couchdb-cleanup.sh on UNIX like systems.

Install dependencies & start the application
1. Install dependencies: npm install
2. Configure REACT_APP_HOSPITALRUN_API=http://localhost:5984 environment variable in .env
3. Run the application npm start

3. Start the application
npm install
npm run start
Open a file named .env and add a line REACT_APP_HOSPITALRUN_API=http://localhost:5984 if you don't have it yet.
Note: To delete the development database, go to the root of the project and run docker-compose down -v --rmi all --remove-orphans
If your branch's packages changed, reinstall the packages before starting the application:
rm -fr node_modules
rm yarn.lock (if you used yarn before)
rm package-lock.json
npm install
npm run start
Note: We no longer support the use of yarn.

4. Before pushing your changes, check locally that your branch passes CI checks

We use Jest + React Testing Library for Behavior-Driven Development Tests
npm run test:ci will run the entire test suite
npm run test:ci <file name> e.g. npm run test:ci src/__tests__/HospitalRun.test.tsx will run that specific test file
npm run test will run the test suite in watch mode

We use ESLint for static program analysis
npm run lint will run the linter
npm run lint:fix will run the linter and fix fixable errors


Released under the [MIT license](LICENSE).
