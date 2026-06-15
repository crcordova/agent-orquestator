# Mobile App

## Architecture Patterns
- Cross-platform: React Native, Flutter, or native (Swift/Kotlin)
- State management: Redux, Zustand, Riverpod, BLoC, or native state
- Navigation: stack, tab, drawer patterns
- API layer: typed API client with caching
- Offline-first: local database + sync

## Key Decisions
- [ ] Platform: iOS, Android, or cross-platform
- [ ] Framework (React Native, Flutter, Swift/SwiftUI, Kotlin/Jetpack Compose)
- [ ] State management approach
- [ ] Navigation library
- [ ] Local storage (SQLite, AsyncStorage, Hive, Realm)
- [ ] Push notification provider
- [ ] Analytics and crash reporting
- [ ] CI/CD for mobile (Fastlane, EAS, App Center)

## Standard Slices
1. Project scaffolding and configuration
2. Navigation structure
3. Design system and theme
4. API client and networking layer
5. Authentication flow
6. Core screens and components
7. State management setup
8. Local storage and caching
9. Push notifications
10. Deep linking
11. Error handling and error boundaries
12. Testing
13. App store configuration

## Testing Strategy
- Unit tests for business logic and utilities
- Widget/component tests for UI components
- Integration tests for screen flows
- E2E tests (Detox, Maestro, XCUITest)
- Snapshot tests for visual regression

## Performance Considerations
- Lazy loading and virtualized lists
- Image optimization and caching
- Bundle size monitoring
- Startup time optimization
- Memory management
- Network request batching

## Platform-Specific Patterns

### React Native
- Expo vs bare workflow
- New Architecture (Fabric + TurboModules)
- Bridgeless mode

### Flutter
- Widget composition
- Platform channels for native code
- State management (Riverpod recommended)

### Native
- SwiftUI/UIKit or Jetpack Compose/XML
- Dependency injection
- Modular architecture
