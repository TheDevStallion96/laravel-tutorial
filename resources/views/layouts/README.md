# Blade Views:

## 1. Main Layout: `app.blade.php`
```blade
<body class="app-body">
    <div class="app-container">
        @include('layouts.navigation')

        <!-- App Heading -->
        @if (isset($header))
            <header class="app-header">
                <div class="header-content">
                    {{ $header }}
                </div>
            </header>
        @endif

        <!-- App Content -->
        <main class="app-main">
            {{ $slot }}
        </main>
    </div>
</body>
```
## 2. Auth Layout: `auth.blade.php`
```blade
<!DOCTYPE html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <meta name="csrf-token" content="{{ csrf_token() }}">

        <title>{{ config('app.name', 'Laravel') }}</title>

        <!-- Fonts -->
        <link rel="preconnect" href="https://fonts.bunny.net">
        <link href="https://fonts.bunny.net/css?family=figtree:400,500,600&display=swap" rel="stylesheet" />

        <!-- Styles -->
        @vite(['resources/css/app.css', 'resources/js/app.js'])
    </head>
    <body class="app-auth-body">
        <div class="app-auth-container">
            <div>
                <a href="/">
                    <x-application-logo class="app-auth-logo" />
                </a>
            </div>

            <div class="app-auth-card">
                {{ $slot }}
            </div>
        </div>
    </body>
</html>
```

# CSS Classes:
## 1. Main Layout:
```postcss
/* File: resources/css/custom.css */

@layer components {
    .app-body {
        @apply font-sans antialiased;
    }

    .app-container {
        @apply min-h-screen bg-gray-100 dark:bg-gray-900;
    }

    .app-header {
        @apply bg-white dark:bg-gray-800 shadow;
    }

    .header-content {
        @apply max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8;
    }
}
```

