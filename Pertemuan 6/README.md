# Source Code
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Bootstrap Layout</title>
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css">
    </head>
    <body class="bg-light">
        <header class="bg-primary text-white p-3">
            <div class="container">
                <h2 class="mb-0">Header</h2>
                <nav class="mt-2">
                    <a href="#" class="btn btn-primary me-2">Home</a>
                    <a href="#" class="btn btn-primary me-2">About</a>
                    <a href="#" class="btn btn-primary me-2">Contact</a>
                </nav>
            </div>
        </header>

        <div class="container my-4">
            <div class="row">
                <aside class="col-md-2 mb-2">
                    <div class="card mb-2">
                        <div class="card-body">
                            <h5 class="card-title">Menu Item 1</h5>
                            <p class="card-text">Quick navigation</p>
                        </div>
                    </div>
                    <div class="card mb-2">
                        <div class="card-body">
                            <h5 class="card-title">Menu Item 2</h5>
                            <p class="card-text">Useful link</p>
                        </div>
                    </div>
                    <div class="card mb-2">
                        <div class="card-body">
                            <h5 class="card-title">Menu Item 3</h5>
                            <p class="card-text">Resource</p>
                        </div>
                    </div>
                </aside>

                <main class="col-md-10">
                    <h3 class="fw-bold md-3">Konten</h3>
                    <div class="row">
                        <div class="col-md-6 mb-3">
                            <div class="card bg-dark text-white h-100">
                                <div class="card-body">
                                    <h5 class="card-title">Feature 1</h5>
                                    <p class="card-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore.</p>
                                    <a href="#" class="btn btn-primary">Learn More</a>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card bg-dark text-white h-100">
                                <div class="card-body">
                                    <h5 class="card-title">Feature 2</h5>
                                    <p class="card-text">Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.</p>
                                    <a href="#" class="btn btn-success">Get started</a>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="card bg-white text-dark mt-3">
                        <div class="card-body">
                            <h5 class="card-title">Main Article</h5>
                            <p class="card-text">
                                Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                                Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. 
                                Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.
                            </p>
                        </div>
                    </div>
                </main>
            </div>
        </div>

        <footer class="bg-secondary text-white py-3">
            <div class="container d-flex justify-content-between">
                <div>
                    <h5 class="mb-1">Footer</h5>
                    <small>© 2024 Your Company. All rights reserved.</small>
                </div>
                <div>
                    <a href="#" class="text-white me-3">Privacy</a>
                    <a href="#" class="text-white me-3">Terms</a>
                    <a href="#" class="text-white">Support</a>
                </div>
            </div>
        </footer>

        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
    </body>
</html>
```
