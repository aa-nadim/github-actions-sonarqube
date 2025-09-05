# GitHub Actions SonarQube

## INSTRUCTIONS for SonarQube
```bash
python3.12 -m venv .venv --without-pip

source .venv/bin/activate
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
deactivate

pip install -r requirements.txt
python3 main.py
flake8 main.py
black main.py
```

## Start SonarQube
```bash
# Start SonarQube
docker-compose up -d

# Check logs
docker-compose logs -f sonarqube
```

## Access SonarQube
- Open browser and go to http://localhost:9000
- Default credentials: admin / admin
- You'll be prompted to change the password


## Configuration for GitHub Actions

### Step 1: Generate SonarQube Token

- Login to SonarQube (http://localhost:9000)
- Go to My Account → Security → Generate Tokens
- Create a new token (e.g., "GitHub Actions")
- Copy the token

### Step 2: Create Project in SonarQube

- Click Create Project → Manually
- Enter project key: github-actions-sonarqube
- Display name: GitHub Actions SonarQube
- Click Set Up

### Step 3: Add GitHub Secrets
- In your GitHub repository:

- Go to Settings → Secrets and variables → Actions
Add these secrets:

- SONAR_TOKEN: The token you generated
- SONAR_HOST_URL: http://your-server-ip:9000 (replace with your actual server IP)


## References



