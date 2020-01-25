# udemy-docker-and-kubernetes-the-complete-guide


**Create React App**

```bash
npx create-react-app frontend
npm run start
```

## Development Environment

**Build Docker for Development Environment**

Not sure what the usecase is, btut we will see.
We tell docker to not mess with /app/nodes_modules.
We could also use docker-compose (`docker-compose up`)

```bash
docker build -f Dockerfile.dev .
docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app 907ccefed97d
```

**Run tests within the container**

```bash
docker run -it 900601ba8071 npm run test
```

We can also create a test container that listens for changes in the tests and reruns the tests automatically.

```bash
docker-compose up -d
```

## Prod Environment

**Build and Run Docker for Prod Environment**

```bash
docker build .
docker run -p 8080:80 527b5ccfbf1c
```

