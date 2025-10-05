<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Leap Cloud Deployment Guide 2025</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 40px 20px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }
        
        h1 {
            color: #667eea;
            font-size: 2.5em;
            margin-bottom: 10px;
            text-align: center;
            font-weight: 700;
        }
        
        h2 {
            color: #764ba2;
            font-size: 1.8em;
            margin-top: 40px;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid #667eea;
        }
        
        h3 {
            color: #555;
            font-size: 1.3em;
            margin-top: 25px;
            margin-bottom: 15px;
            font-weight: 600;
        }
        
        .intro {
            text-align: center;
            color: #666;
            margin-bottom: 40px;
            font-size: 1.1em;
        }
        
        .components-list {
            background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
        }
        
        .components-list ul {
            list-style: none;
            padding-left: 0;
        }
        
        .components-list li {
            padding: 8px 0;
            padding-left: 30px;
            position: relative;
            font-size: 1.05em;
        }
        
        .components-list li:before {
            content: "▶";
            position: absolute;
            left: 10px;
            color: #667eea;
            font-size: 0.8em;
        }
        
        .code-block {
            background: #2d2d2d;
            color: #f8f8f2;
            padding: 20px;
            border-radius: 8px;
            margin: 15px 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
            font-size: 0.95em;
            line-height: 1.5;
            position: relative;
            border-left: 4px solid #667eea;
        }
        
        .code-block code {
            display: block;
        }
        
        .warning {
            background: #fff3cd;
            border-left: 4px solid #ffc107;
            padding: 15px;
            margin: 15px 0;
            border-radius: 5px;
            display: flex;
            align-items: center;
        }
        
        .warning::before {
            content: "⚠️";
            font-size: 1.5em;
            margin-right: 15px;
        }
        
        .step {
            margin: 20px 0;
        }
        
        .step-title {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 10px 15px;
            border-radius: 5px;
            font-weight: 600;
            margin-bottom: 10px;
            display: inline-block;
        }
        
        .section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 15px;
            margin: 30px 0;
            border: 2px solid #e9ecef;
        }
        
        .component-number {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 10px;
            font-size: 1.2em;
        }
        
        .component-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .example-box {
            background: linear-gradient(135deg, #11998e15 0%, #38ef7d15 100%);
            border: 2px solid #11998e;
            padding: 25px;
            border-radius: 10px;
            margin: 30px 0;
        }
        
        .reminders {
            background: linear-gradient(135deg, #f093fb15 0%, #f5576c15 100%);
            border: 2px solid #f093fb;
            padding: 25px;
            border-radius: 10px;
            margin-top: 30px;
        }
        
        .reminders ul {
            margin-left: 20px;
            margin-top: 15px;
        }
        
        .reminders li {
            margin: 10px 0;
            color: #555;
        }
        
        hr {
            border: none;
            border-top: 2px solid #e9ecef;
            margin: 40px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>☁️ Leap Cloud Deployment Guide 2025</h1>
        <p class="intro">Complete containerization guide for deploying applications to JFrog Artifactory</p>
        
        <div class="section">
            <h2>Prerequisites</h2>
            <h3>Login to JFrog Artifactory</h3>
            <div class="code-block">
                <code>docker login &lt;artifactory_URL&gt;</code>
            </div>
            <p>Enter your username and password when prompted.</p>
        </div>

        <hr>

        <h2>Application Components</h2>
        <div class="components-list">
            <p style="margin-bottom: 15px; font-weight: 600;">This guide covers containerization for 4 applications:</p>
            <ul>
                <li><strong>Frontend</strong> (Angular)</li>
                <li><strong>Midtier</strong> (Node)</li>
                <li><strong>Backend</strong> (Spring Boot)</li>
                <li><strong>FMTS</strong> (Node)</li>
            </ul>
        </div>

        <hr>

        <div class="section">
            <div class="component-header">
                <span class="component-number">1</span>
                <h2 style="margin: 0; border: none; padding: 0;">Frontend - Angular</h2>
            </div>
            
            <h3>Setup</h3>
            <p>Navigate to the frontend folder:</p>
            <div class="code-block">
                <code>cd frontend</code>
            </div>
            <p>Create a Dockerfile and copy content from <code>&lt;git_url&gt;</code></p>
            
            <div class="warning">
                <strong>Important:</strong> Update the ports according to your application configuration
            </div>

            <h3>Build, Tag & Push</h3>
            
            <div class="step">
                <div class="step-title">Step 1: Build the Docker image</div>
                <div class="code-block">
                    <code>docker build -t &lt;frontend-projectname-corpid&gt;:&lt;image_version&gt; .</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 2: Tag the image for JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker tag &lt;frontend-projectname-corpid&gt;:&lt;image_version&gt; &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;frontend-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 3: Push the image to JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker push &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;frontend-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>
        </div>

        <hr>

        <div class="section">
            <div class="component-header">
                <span class="component-number">2</span>
                <h2 style="margin: 0; border: none; padding: 0;">Midtier - Node</h2>
            </div>
            
            <h3>Setup</h3>
            <p>Navigate to the midtier folder:</p>
            <div class="code-block">
                <code>cd midtier</code>
            </div>
            <p>Create a Dockerfile and copy content from <code>&lt;git_url&gt;</code></p>
            
            <div class="warning">
                <strong>Important:</strong> Update the ports according to your application configuration
            </div>

            <h3>Build, Tag & Push</h3>
            
            <div class="step">
                <div class="step-title">Step 1: Build the Docker image</div>
                <div class="code-block">
                    <code>docker build -t &lt;midtier-projectname-corpid&gt;:&lt;image_version&gt; .</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 2: Tag the image for JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker tag &lt;midtier-projectname-corpid&gt;:&lt;image_version&gt; &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;midtier-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 3: Push the image to JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker push &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;midtier-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>
        </div>

        <hr>

        <div class="section">
            <div class="component-header">
                <span class="component-number">3</span>
                <h2 style="margin: 0; border: none; padding: 0;">Backend - Spring Boot</h2>
            </div>
            
            <h3>Setup</h3>
            <p>Navigate to the Spring Boot folder:</p>
            <div class="code-block">
                <code>cd springboot</code>
            </div>
            <p>Create a Dockerfile and copy content from <code>&lt;git_url&gt;</code></p>
            
            <div class="warning">
                <strong>Important:</strong> Update the ports according to your application configuration
            </div>

            <h3>Build, Tag & Push</h3>
            
            <div class="step">
                <div class="step-title">Step 1: Build the Docker image</div>
                <div class="code-block">
                    <code>docker build -t &lt;backend-projectname-corpid&gt;:&lt;image_version&gt; .</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 2: Tag the image for JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker tag &lt;backend-projectname-corpid&gt;:&lt;image_version&gt; &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;backend-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 3: Push the image to JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker push &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;backend-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>
        </div>

        <hr>

        <div class="section">
            <div class="component-header">
                <span class="component-number">4</span>
                <h2 style="margin: 0; border: none; padding: 0;">FMTS - Node</h2>
            </div>
            
            <h3>Setup</h3>
            <p>Navigate to the FMTS folder:</p>
            <div class="code-block">
                <code>cd fmts</code>
            </div>
            <p>Create a Dockerfile and copy content from <code>&lt;git_url&gt;</code></p>
            
            <div class="warning">
                <strong>Important:</strong> Update the ports according to your application configuration
            </div>

            <h3>Build, Tag & Push</h3>
            
            <div class="step">
                <div class="step-title">Step 1: Build the Docker image</div>
                <div class="code-block">
                    <code>docker build -t &lt;fmts-projectname-corpid&gt;:&lt;image_version&gt; .</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 2: Tag the image for JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker tag &lt;fmts-projectname-corpid&gt;:&lt;image_version&gt; &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;fmts-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>

            <div class="step">
                <div class="step-title">Step 3: Push the image to JFrog Artifactory</div>
                <div class="code-block">
                    <code>docker push &lt;jfrog-url&gt;/&lt;fse-group-classroom&gt;/&lt;fmts-projectname-corpid&gt;:&lt;image_version&gt;</code>
                </div>
            </div>
        </div>

        <hr>

        <div class="example-box">
            <h2 style="color: #11998e; margin-top: 0;">💡 Example Usage</h2>
            <p style="margin-bottom: 15px;">Here's a complete example for the frontend component:</p>
            <div class="code-block">
                <code># Build
docker build -t frontend-marshal-a900003:1.0 .

# Tag
docker tag frontend-marshal-a900003:1.0 rahulraj.jfrog.io/rahul-repo/frontend-marshal-a900003:1.0

# Push
docker push rahulraj.jfrog.io/rahul-repo/frontend-marshal-a900003:1.0</code>
            </div>
        </div>

        <div class="reminders">
            <h2 style="color: #f093fb; margin-top: 0;">📋 Key Reminders</h2>
            <ul>
                <li>Always navigate to the correct folder before building Docker images</li>
                <li>Ensure ports in Dockerfile match your application configuration</li>
                <li>Use consistent naming conventions across all components</li>
                <li>Replace placeholder values with your actual project details</li>
            </ul>
        </div>
    </div>
</body>
</html>