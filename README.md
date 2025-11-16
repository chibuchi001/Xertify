<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Xertify - Decentralized Certificate Management Platform</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 60px 40px;
            text-align: center;
        }

        .header h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .header .subtitle {
            font-size: 1.3rem;
            opacity: 0.95;
            max-width: 800px;
            margin: 0 auto;
        }

        .badges {
            display: flex;
            gap: 10px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .badge {
            background: rgba(255,255,255,0.2);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            backdrop-filter: blur(10px);
        }

        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 60px;
        }

        .section-title {
            font-size: 2.5rem;
            color: #667eea;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid #667eea;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-subtitle {
            font-size: 1.8rem;
            color: #764ba2;
            margin: 30px 0 15px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .card h3 {
            color: #667eea;
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .card ul {
            list-style: none;
            padding-left: 0;
        }

        .card li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
        }

        .card li:before {
            content: "✓";
            position: absolute;
            left: 0;
            color: #10b981;
            font-weight: bold;
        }

        .feature-box {
            background: white;
            border: 2px solid #667eea;
            border-radius: 10px;
            padding: 20px;
            margin: 15px 0;
        }

        .feature-box h4 {
            color: #764ba2;
            margin-bottom: 10px;
        }

        .tech-stack {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .tech-item {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            font-weight: 600;
        }

        .code-block {
            background: #1e1e1e;
            color: #d4d4d4;
            padding: 20px;
            border-radius: 10px;
            overflow-x: auto;
            margin: 15px 0;
            font-family: 'Courier New', monospace;
            font-size: 0.9rem;
        }

        .code-block .comment {
            color: #6a9955;
        }

        .code-block .keyword {
            color: #569cd6;
        }

        .code-block .string {
            color: #ce9178;
        }

        .architecture {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 15px;
            margin: 30px 0;
            border: 2px dashed #667eea;
        }

        .flow-diagram {
            text-align: center;
            font-family: monospace;
            line-height: 2;
            background: white;
            padding: 20px;
            border-radius: 10px;
        }

        .cta-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 50px;
            border-radius: 15px;
            text-align: center;
            margin: 40px 0;
        }

        .cta-button {
            background: white;
            color: #667eea;
            padding: 15px 40px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            display: inline-block;
            margin: 10px;
            transition: transform 0.3s ease;
        }

        .cta-button:hover {
            transform: scale(1.05);
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
        }

        .stat-card .number {
            font-size: 3rem;
            font-weight: bold;
            display: block;
            margin-bottom: 10px;
        }

        .stat-card .label {
            font-size: 1rem;
            opacity: 0.9;
        }

        .roadmap {
            position: relative;
            padding-left: 30px;
        }

        .roadmap:before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(180deg, #667eea 0%, #764ba2 100%);
        }

        .roadmap-item {
            position: relative;
            margin-bottom: 30px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 10px;
        }

        .roadmap-item:before {
            content: "";
            position: absolute;
            left: -37px;
            top: 25px;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: #667eea;
            border: 3px solid white;
            box-shadow: 0 0 0 3px #667eea;
        }

        .footer {
            background: #1e1e1e;
            color: white;
            padding: 40px;
            text-align: center;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 20px 0;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #667eea;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: #764ba2;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .header .subtitle {
                font-size: 1rem;
            }
            
            .content {
                padding: 20px;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>🎓 Xertify</h1>
            <p class="subtitle">Decentralized Certificate Management Platform Built on Polkadot</p>
            <div class="badges">
                <span class="badge">🔗 Polkadot</span>
                <span class="badge">⚛️ React</span>
                <span class="badge">🟢 Node.js</span>
                <span class="badge">🍃 MongoDB</span>
                <span class="badge">🦀 Rust/ink!</span>
                <span class="badge">🌐 Web3</span>
            </div>
        </div>

        <!-- Content -->
        <div class="content">
            <!-- Overview -->
            <section class="section">
                <h2 class="section-title">🎯 Overview</h2>
                <p style="font-size: 1.1rem; line-height: 1.8;">
                    <strong>Xertify</strong> is a user-centric, decentralized certificate management platform built on the Polkadot blockchain ecosystem. It empowers educational institutions, organizations, and individuals to create, issue, and verify digital certificates as NFTs, ensuring permanent, tamper-proof records stored on-chain.
                </p>
            </section>

            <!-- Problem Statement -->
            <section class="section">
                <h2 class="section-title">🔍 Problem Statement</h2>
                <div class="stats">
                    <div class="stat-card">
                        <span class="number">85%</span>
                        <span class="label">Employers encounter fraudulent credentials</span>
                    </div>
                    <div class="stat-card">
                        <span class="number">$600M+</span>
                        <span class="label">Lost annually to credential fraud</span>
                    </div>
                    <div class="stat-card">
                        <span class="number">3-7</span>
                        <span class="label">Days average verification time</span>
                    </div>
                </div>

                <div class="grid">
                    <div class="card">
                        <h3>❌ Certificate Fraud</h3>
                        <p>Easy to forge physical or digital certificates without blockchain verification.</p>
                    </div>
                    <div class="card">
                        <h3>❌ Verification Difficulties</h3>
                        <p>Employers spend time and money verifying credentials through intermediaries.</p>
                    </div>
                    <div class="card">
                        <h3>❌ Centralized Control</h3>
                        <p>Certificate issuers have complete control over validity and access.</p>
                    </div>
                    <div class="card">
                        <h3>❌ No True Ownership</h3>
                        <p>Recipients don't truly own their credentials and can't transfer them.</p>
                    </div>
                </div>
            </section>

            <!-- Solution -->
            <section class="section">
                <h2 class="section-title">💡 Our Solution</h2>
                <p style="font-size: 1.1rem; margin-bottom: 30px;">
                    Xertify leverages <strong>Polkadot's decentralized infrastructure</strong> to create a user-centric certificate platform that prioritizes user interests and has real-world impact.
                </p>

                <div class="grid">
                    <div class="card">
                        <h3>✅ Ensures Authenticity</h3>
                        <ul>
                            <li>Cryptographically signed certificates</li>
                            <li>Immutable blockchain storage</li>
                            <li>Tamper-proof records</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>✅ True Ownership</h3>
                        <ul>
                            <li>Recipients own NFT certificates</li>
                            <li>Full control over sharing</li>
                            <li>Portable across platforms</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>✅ Instant Verification</h3>
                        <ul>
                            <li>Blockchain-based verification</li>
                            <li>No intermediaries needed</li>
                            <li>Global accessibility</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>✅ Cost Reduction</h3>
                        <ul>
                            <li>Free verification</li>
                            <li>Low minting costs</li>
                            <li>No subscription fees</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- Key Features -->
            <section class="section">
                <h2 class="section-title">✨ Key Features</h2>

                <h3 class="section-subtitle">For Certificate Issuers</h3>
                <div class="feature-box">
                    <h4>🎨 Customizable Templates</h4>
                    <p>Multiple professional certificate designs with custom branding options.</p>
                </div>
                <div class="feature-box">
                    <h4>💰 Flexible Minting</h4>
                    <p>Choose between free or paid certificate minting with integrated payments.</p>
                </div>
                <h3 class="section-subtitle">For Certificate Recipients</h3>
                <div class="feature-box">
                    <h4>🏆 NFT Ownership</h4>
                    <p>Certificates as tradeable NFTs stored in your Polkadot wallet.</p>
                </div>
                <div class="feature-box">
                    <h4>🔗 Portable Credentials</h4>
                    <p>Take your certificates anywhere, use them across platforms.</p>
                </div>
                <div class="feature-box">
                    <h4>✅ Instant Verification</h4>
                    <p>Share verification links that instantly prove authenticity.</p>
                </div>
            </section>

            <!-- Tech Stack -->
            <section class="section">
                <h2 class="section-title">🛠️ Tech Stack</h2>
                
                <h3 class="section-subtitle">Frontend</h3>
                <div class="tech-stack">
                    <div class="tech-item">React 18.x</div>
                    <div class="tech-item">Redux Toolkit</div>
                    <div class="tech-item">TailwindCSS 3.x</div>
                    <div class="tech-item">React Router 6.x</div>
                </div>

                <h3 class="section-subtitle">Backend</h3>
                <div class="tech-stack">
                    <div class="tech-item">Node.js 18.x</div>
                    <div class="tech-item">Express 4.x</div>
                    <div class="tech-item">MongoDB 6.x</div>
                    <div class="tech-item">JWT Auth</div>
                </div>

                <h3 class="section-subtitle">Blockchain (Polkadot)</h3>
                <div class="tech-stack">
                    <div class="tech-item">ink! Smart Contracts</div>
                    <div class="tech-item">Substrate Framework</div>
                    <div class="tech-item">Polkadot.js API</div>
                    <div class="tech-item">IPFS Storage</div>
                </div>
            </section>

            <!-- Architecture -->
            <section class="section">
                <h2 class="section-title">🏗️ Architecture</h2>
                <div class="architecture">
                    <div class="flow-diagram">
                        <div style="font-weight: bold; font-size: 1.2rem; margin-bottom: 20px;">System Architecture</div>
                        ┌─────────────────────┐<br>
                        │   FRONTEND (React)   │<br>
                        │   Dashboard, Builder │<br>
                        └─────────────────────┘<br>
                        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↕ REST API<br>
                        ┌─────────────────────┐<br>
                        │  BACKEND (Node.js)   │<br>
                        │  Auth, Certificates  │<br>
                        └─────────────────────┘<br>
                        &nbsp;&nbsp;&nbsp;↕&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↕&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↕<br>
                        ┌──────┐  ┌────────┐  ┌──────┐<br>
                        │MongoDB│  │Polkadot│  │ IPFS │<br>
                        │  DB   │  │  Chain │  │Pinata│<br>
                        └──────┘  └────────┘  └──────┘
                    </div>
                </div>
            </section>

            <!-- Getting Started -->
            <section class="section">
                <h2 class="section-title">🚀 Getting Started</h2>
                
                <h3 class="section-subtitle">Prerequisites</h3>
                <div class="card">
                    <ul>
                        <li>Node.js v18.x or higher</li>
                        <li>MongoDB v6.x or higher</li>
                        <li>Rust & Cargo (for smart contracts)</li>
                        <li>cargo-contract CLI tool</li>
                        <li>Polkadot.js Browser Extension</li>
                    </ul>
                </div>

                <h3 class="section-subtitle">Installation</h3>
                <div class="code-block">
                    <span class="comment"># Clone the repository</span><br>
                    git clone https://github.com/yourusername/xertify.git<br>
                    cd xertify<br><br>
                    
                    <span class="comment"># Install backend dependencies</span><br>
                    cd backend<br>
                    npm install<br><br>
                    
                    <span class="comment"># Install frontend dependencies</span><br>
                    cd ../frontend<br>
                    npm install<br><br>
                    
                    <span class="comment"># Build smart contracts</span><br>
                    cd ../polkadot-certificates/cert_nft<br>
                    cargo contract build --release
                </div>

                <h3 class="section-subtitle">Configuration</h3>
                <div class="code-block">
                    <span class="comment"># Backend .env file</span><br>
                    <span class="keyword">PORT</span>=<span class="string">5000</span><br>
                    <span class="keyword">MONGODB_URI</span>=<span class="string">mongodb://localhost:27017/xertify</span><br>
                    <span class="keyword">JWT_SECRET</span>=<span class="string">your-secret-key</span><br>
                    <span class="keyword">POLKADOT_WS_ENDPOINT</span>=<span class="string">ws://127.0.0.1:9944</span><br>
                    <span class="keyword">PINATA_API_KEY</span>=<span class="string">your-api-key</span>
                </div>

                <h3 class="section-subtitle">Running the Application</h3>
                <div class="code-block">
                    <span class="comment"># Start backend (in backend directory)</span><br>
                    npm run dev<br><br>
                    
                    <span class="comment"># Start frontend (in frontend directory)</span><br>
                    npm run dev<br><br>
                    
                    <span class="comment"># Access at:</span><br>
                    <span class="comment"># Frontend: http://localhost:3000</span><br>
                    <span class="comment"># Backend: http://localhost:5000</span>
                </div>
            </section>

            <!-- Web3 Principles -->
            <section class="section">
                <h2 class="section-title">🌐 Web3 Principles & User-Centric Design</h2>
                
                <div class="grid">
                    <div class="card">
                        <h3>🔓 Decentralization</h3>
                        <ul>
                            <li>Certificates on Polkadot blockchain</li>
                            <li>IPFS for metadata storage</li>
                            <li>No single point of failure</li>
                            <li>Censorship-resistant</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>👤 User Ownership</h3>
                        <ul>
                            <li>Recipients own NFT certificates</li>
                            <li>Full control over credentials</li>
                            <li>Transferable and tradeable</li>
                            <li>No platform lock-in</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>🔍 Transparency</h3>
                        <ul>
                            <li>All transactions on-chain</li>
                            <li>Public verification available</li>
                            <li>Open-source smart contracts</li>
                            <li>Auditable history</li>
                        </ul>
                    </div>
                    <div class="card">
                        <h3>🔒 Privacy</h3>
                        <ul>
                            <li>User controls data sharing</li>
                            <li>Selective disclosure</li>
                            <li>No centralized storage</li>
                            <li>GDPR compliant</li>
                        </ul>
                    </div>
                </div>

                <h3 class="section-subtitle">Real-World Impact</h3>
                <div class="feature-box">
                    <h4>🌍 For Developing Countries</h4>
                    <p>Accessible to anyone with internet, low-cost verification, mobile-first design, free basic tier for education.</p>
                </div>
                <div class="feature-box">
                    <h4>🎓 For Educational Institutions</h4>
                    <p>Reduce administrative costs, instant certificate issuance, prevent diploma mills, track graduate success.</p>
                </div>
                <div class="feature-box">
                    <h4>💼 For Job Seekers</h4>
                    <p>Verifiable credentials, faster hiring process, global opportunities, build verifiable portfolio.</p>
                </div>
                <div class="feature-box">
                    <h4>🏢 For Employers</h4>
                    <p>Save verification time, trust candidate credentials, hire globally with confidence, reduce HR costs.</p>
                </div>
            </section>

            <!-- Roadmap -->
            <section class="section">
                <h2 class="section-title">🗺️ Roadmap</h2>
                <div class="roadmap">
                    <div class="roadmap-item">
                        <h3>Q1 2025 ✅</h3>
                        <ul>
                            <li>Core platform development</li>
                            <li>Smart contract deployment</li>
                            <li>Basic NFT minting</li>
                            <li>Email notifications</li>
                        </ul>
                    </div>
                    <div class="roadmap-item">
                        <h3>Q2 2025 🚧</h3>
                        <ul>
                            <li>Mobile app (iOS/Android)</li>
                            <li>Batch certificate issuance</li>
                            <li>Certificate marketplace</li>
                            <li>Multi-language support</li>
                        </ul>
                    </div>
                    <div class="roadmap-item">
                        <h3>Q3 2025 📋</h3>
                        <ul>
                            <li>Cross-parachain support</li>
                            <li>Advanced analytics</li>
                            <li>Third-party API</li>
                            <li>Enterprise features</li>
                        </ul>
                    </div>
                    <div class="roadmap-item">
                        <h3>Q4 2025 🎯</h3>
                        <ul>
                            <li>AI-powered fraud detection</li>
                            <li>Skill matching system</li>
                            <li>Job board integration</li>
                            <li>Global partnerships</li>
                        </ul>
                    </div>
                </div>
            </section>

            <!-- CTA -->
            <div class="cta-section">
                <h2 style="font-size: 2.5rem; margin-bottom: 20px;">Ready to Get Started?</h2>
                <p style="font-size: 1.2rem; margin-bottom: 30px;">Join the future of digital credentials with Xertify</p>
                <a href="#" class="cta-button">🚀 Start Creating Certificates</a>
                <a href="#" class="cta-button">📖 Read Documentation</a>
                <a href="#" class="cta-button">💬 Join Community</a>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <h3 style="margin-bottom: 20px;">📞 Contact & Community</h3>
            <div class="footer-links">
                <a href="#">GitHub</a>
                <a href="#">Discord</a>
                <a href="#">Twitter</a>
                <a href="#">Documentation</a>
                <a href="#">Medium Blog</a>
                <a href="#">Support</a>
            </div>
            <p style="margin-top: 30px; opacity: 0.8;">
                Made with ❤️ by the Xertify Team<br>
                Built on Polkadot | Powered by Web3
            </p>
            <p style="margin-top: 20px; font-size: 0.9rem; opacity: 0.6;">
                © 2025 Xertify. Licensed under MIT License.
            </p>
        </div>
    </div>
</body>
</html>
