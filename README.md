# SharedUI for Android

## 📝 Overview

AndroidSharedUI is a comprehensive Jetpack Compose UI library providing reusable components that follow Salesforce Lightning Design System guidelines. The library includes a complete theming framework with support for multiple design systems, comprehensive accessibility features, and production-ready components for Android applications.

### Key Features

- **Production-Ready Components**: Organized into multiple categories covering all common UI patterns
- **Complete Theming System**: Colors, Typography, Shapes, Dimensions, and Shadows with multiple design system support
- **Multiple Design Systems**: Built-in Salesforce Cosmos and Square themes
- **SLDS Compliant**: Follows Salesforce Lightning Design System Plus guidelines
- **Jetpack Compose Native**: Built specifically for modern Android development
- **Accessibility First**: Comprehensive accessibility support built into all components
- **Extensive Documentation**: Complete API documentation with practical examples for every component

### Architecture Overview

The library is organized into six main component categories:

- **Core UI Components** (4): Button, Card, Avatar, Badge
- **Interactive Components** (5): Checkbox, Combobox, Toast, Tooltip, ModalSheet
- **Layout Components** (4): BaseRow, BadgeRow, CollapsibleCard, SearchRow
- **Display Components** (5): Footer, NoContent, ToggleTile, ContactRow, FieldValueTile
- **Selection Components** (2): SingleSelectionList, SelectionListItem
- **Icon Components** (1): BaseIcon with full SLDS icon support

## 🚀 Installation

### Gradle

Add SharedUI to your project's `build.gradle`:

```groovy
dependencies {
    implementation 'com.salesforce.android:sharedui:1.0.0'
}
```

### Requirements

- Android SDK 24 (Android 7.0) or higher
- Kotlin 1.9+
- Jetpack Compose 1.5+

## 📋 Component Summary

| Component | Description |
|-----------|-------------|
| **Avatar** | Displays a user's initials in a circular avatar, supporting multiple sizes |
| **Badge** | Shows a badge with a count, styled for info, success, warning, or error |
| **BadgeRow** | Interactive row with icon, title, and badge count, for lists or filters |
| **BaseIcon** | Displays a Lightning Design System icon with optional color and size |
| **BaseRow** | Flexible row layout with optional leading/trailing content and click action |
| **Button** | Configurable button for actions, supporting icons, styles, and sizes |
| **Card** | Container for grouping content, often with padding and elevation |
| **Checkbox** | Checkbox supporting checked, unchecked, and indeterminate states |
| **CollapsibleCard** | Card with expandable/collapsible content and header |
| **Combobox** | Dropdown for selecting from a list of options, with optional placeholder |
| **ContactRow** | Row for displaying contact info with avatar and subtitle |
| **FieldValueTile** | Tile for displaying a field and value, with edit and delete actions |
| **Footer** | Footer for lists, cards, or empty states, with a label and click action |
| **ModalSheet** | Modal bottom sheet with header, title, and dismiss action |
| **NoContent** | Displays empty, error, or loading state with optional action |
| **SearchRow** | Row for search history, suggestions, or invoking a search |
| **SelectionListItem** | List item for selection lists, supporting icons and dividers |
| **SingleSelectionList** | List for single selection, often used in modal sheets |
| **Toast** | Alert/toast for feedback, with optional action and close |
| **Tooltip** | Contextual information tooltips with multiple anchor positions |
| **ToggleTile** | Tile for quick filters or status, selectable and styled |
| **Toolbar** | Customizable toolbar component with navigation and actions |

## 🎨 Theme System

SharedUI includes a comprehensive theming system based on Salesforce Cosmos design tokens:

### Using Themes

```kotlin
import com.salesforce.android.sharedui.theme.SalesforceCosmosTheme
import com.salesforce.android.sharedui.components.*

@Composable
fun MyApp() {
    SalesforceCosmosTheme {
        // Your app content here
        MyScreen()
    }
}
```

### Theme Components

- **Colors**: Primary, secondary, success, warning, error, neutral palettes
- **Typography**: Complete type scale with support for Material You dynamic color
- **Shapes**: Consistent corner radius and shape definitions
- **Dimensions**: Standard spacing and sizing scales
- **Shadows**: Elevation system for depth and hierarchy

### Custom Themes

```kotlin
import com.salesforce.android.sharedui.theme.SharedUITheme

@Composable
fun CustomThemedApp() {
    SharedUITheme(
        colors = MyCustomColors,
        typography = MyCustomTypography,
        shapes = MyCustomShapes
    ) {
        // Your app content
    }
}
```

## 💡 Quick Start Example

```kotlin
import androidx.compose.foundation.layout.*
import androidx.compose.runtime.*
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp
import com.salesforce.android.sharedui.components.*
import com.salesforce.android.sharedui.theme.SalesforceCosmosTheme

@Composable
fun ExampleScreen() {
    var showToast by remember { mutableStateOf(false) }

    SalesforceCosmosTheme {
        Column(
            modifier = Modifier
                .fillMaxSize()
                .padding(16.dp),
            verticalArrangement = Arrangement.spacedBy(16.dp)
        ) {
            Button(
                text = "Primary Button",
                style = ButtonStyle.Primary,
                onClick = { showToast = true }
            )

            Card(
                modifier = Modifier.fillMaxWidth()
            ) {
                Column(
                    modifier = Modifier.padding(16.dp),
                    verticalArrangement = Arrangement.spacedBy(8.dp)
                ) {
                    Text(
                        text = "Card Title",
                        style = MaterialTheme.typography.titleMedium
                    )
                    Text(
                        text = "Card content goes here",
                        style = MaterialTheme.typography.bodyMedium
                    )
                }
            }

            Avatar(
                initials = "JD",
                size = AvatarSize.Large
            )

            if (showToast) {
                Toast(
                    message = "Action completed successfully!",
                    type = ToastType.Success,
                    onDismiss = { showToast = false }
                )
            }
        }
    }
}
```

## ♿️ Accessibility

All SharedUI components are built with accessibility as a priority:

- **TalkBack Support**: Comprehensive screen reader support with meaningful content descriptions
- **Touch Targets**: Minimum 48dp touch targets on all interactive elements
- **Color Contrast**: WCAG AA compliant color combinations
- **State Descriptions**: Clear indication of component states for assistive technologies
- **Keyboard Navigation**: Full keyboard navigation support where applicable
- **Dynamic Font Scaling**: Respect user's system font size preferences

## 🧪 Testing

SharedUI components are designed to be testable:

```kotlin
@Test
fun testButtonClick() {
    composeTestRule.setContent {
        Button(
            text = "Test Button",
            style = ButtonStyle.Primary,
            onClick = { /* handle click */ }
        )
    }

    composeTestRule
        .onNodeWithText("Test Button")
        .performClick()
}
```

## 📄 License

SharedUI is available under the terms specified in the [TERMS OF USE](TERMS%20OF%20USE) file.

Copyright 2026 Salesforce, Inc. All rights reserved.

## 🤝 Support

For bug reports and feature requests, please use the GitHub Issues section of this repository.

For Salesforce employees: Please refer to internal documentation for contribution guidelines and development setup.

## 🔗 Related Projects

- [SLDSIcons-Android](https://github.com/salesforce/SLDSIcons-Android) - Salesforce Lightning Design System icon library for Android
- [Salesforce Lightning Design System](https://www.lightningdesignsystem.com/) - The official design system

## 📚 Additional Resources

- [Jetpack Compose Documentation](https://developer.android.com/jetpack/compose)
- [Material Design 3](https://m3.material.io/)
- [Android Accessibility](https://developer.android.com/guide/topics/ui/accessibility)

---

**Note**: This library is provided as-is for use in mobile applications. See the TERMS OF USE for complete details on usage, warranty, and liability.
