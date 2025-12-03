<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>React Portfolio</title>
    <!-- React Framework -->
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <!-- Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        .component { border: 2px solid #646cff; padding: 20px; margin: 10px 0; }
        .react-app { min-height: 100vh; }
        .feature-card { transition: transform 0.3s; }
        .feature-card:hover { transform: translateY(-5px); }
    </style>
</head>
<body>
    <div id="root" class="react-app"></div>

    <script type="text/babel">
        // Component 1: Header
        function Header() {
            return (
                <nav className="navbar navbar-expand-lg navbar-light bg-light">
                    <div className="container">
                        <a className="navbar-brand" href="#"><i className="fas fa-code"></i> ReactPortfolio</a>
                    </div>
                </nav>
            );
        }

        // Component 2: Hero
        function Hero() {
            return (
                <section className="bg-primary text-white py-5">
                    <div className="container py-5">
                        <h1 className="display-4">React Developer</h1>
                        <p>Built with React Framework & Components</p>
                    </div>
                </section>
            );
        }

        // Component 3: Counter (Interactive Feature)
        function Counter() {
            const [count, setCount] = React.useState(0);
            
            return (
                <div className="component text-center my-4">
                    <h3>React Counter Component</h3>
                    <div className="my-3">
                        <button className="btn btn-primary me-2" onClick={() => setCount(count - 1)}>-</button>
                        <span className="h4 mx-3">{count}</span>
                        <button className="btn btn-primary me-2" onClick={() => setCount(count + 1)}>+</button>
                    </div>
                    <button className="btn btn-secondary" onClick={() => setCount(0)}>Reset</button>
                </div>
            );
        }

        // Component 4: Features
        function Features() {
            const features = [
                { title: "React Components", desc: "Component-based architecture" },
                { title: "State Management", desc: "useState hooks for data" },
                { title: "W3C Valid", desc: "Clean HTML structure" },
                { title: "Responsive", desc: "Works on all devices" }
            ];
            
            return (
                <section className="py-5">
                    <div className="container">
                        <h2 className="text-center mb-4">Framework Features</h2>
                        <div className="row">
                            {features.map((feature, index) => (
                                <div className="col-md-3 mb-3" key={index}>
                                    <div className="feature-card card h-100">
                                        <div className="card-body text-center">
                                            <h5>{feature.title}</h5>
                                            <p>{feature.desc}</p>
                                        </div>
                                    </div>
                                </div>
                            ))}
                        </div>
                    </div>
                </section>
            );
        }

        // Component 5: Contact Form
        function ContactForm() {
            const [formData, setFormData] = React.useState({ name: '', email: '' });
            const [submitted, setSubmitted] = React.useState(false);
            
            const handleSubmit = (e) => {
                e.preventDefault();
                setSubmitted(true);
                setTimeout(() => setSubmitted(false), 3000);
            };
            
            return (
                <section className="py-5 bg-light">
                    <div className="container">
                        <h2 className="text-center mb-4">Contact</h2>
                        <div className="row justify-content-center">
                            <div className="col-md-6">
                                {submitted ? (
                                    <div className="alert alert-success">Message Sent!</div>
                                ) : (
                                    <form onSubmit={handleSubmit}>
                                        <input className="form-control mb-3" placeholder="Name" 
                                               value={formData.name} 
                                               onChange={(e) => setFormData({...formData, name: e.target.value})} />
                                        <input className="form-control mb-3" placeholder="Email" type="email"
                                               value={formData.email}
                                               onChange={(e) => setFormData({...formData, email: e.target.value})} />
                                        <button type="submit" className="btn btn-primary w-100">Send</button>
                                    </form>
                                )}
                            </div>
                        </div>
                    </div>
                </section>
            );
        }

        // Component 6: Footer
        function Footer() {
            return (
                <footer className="bg-dark text-white py-4">
                    <div className="container text-center">
                        <p>React Framework Portfolio - W3C Validated</p>
                    </div>
                </footer>
            );
        }

        // Main App Component
        function App() {
            React.useEffect(() => {
                console.log("Framework Features:");
                console.log("1. React Components");
                console.log("2. State Management");
                console.log("3. Form Handling");
                console.log("4. Responsive Design");
            }, []);
            
            return (
                <>
                    <Header />
                    <Hero />
                    <div className="container">
                        <Counter />
                    </div>
                    <Features />
                    <ContactForm />
                    <Footer />
                </>
            );
        }

        // Render React App
        ReactDOM.render(<App />, document.getElementById('root'));
    </script>
    
    <!-- Font Awesome -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
