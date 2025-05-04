# Stage1:
FROM ubuntu

WORKDIR /app

RUN apt update

RUN apt install -y curl

RUN curl -sL https://deb.nodesource.com/setup_16.x | bash

RUN apt install -y nodejs

# Copy source code
COPY . .

# Install dependencies
RUN npm install

# Build the static files
RUN npm run build


# Install 'serve' globally
RUN npm install -g serve


# Start the server on port 5000
CMD ["serve", "-s", "-l", "5000", "build"]
