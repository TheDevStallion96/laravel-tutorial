# Layout Components

1. Main Layout: `app.blade.php`
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

## CSS Classes:
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

