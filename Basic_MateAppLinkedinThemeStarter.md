import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

/// --------------------
/// COLORS
/// --------------------
class AppColors {
  static const Color primaryBlue = Color(0xFF0A66C2); // LinkedIn brand blue
  static const Color accentBlue = Color(0xFF70B5F9); // lighter blue
  static const Color darkBlue = Color(0xFF004182); // deep navy

  static const Color grey = Color(0xFF86888A);
  static const Color lightGrey = Color(0xFFF3F2EF);
  static const Color dividerGrey = Color(0xFFDCDCDC);

  static const Color successGreen = Color(0xFF228B22);
  static const Color warningOrange = Color(0xFFFFA500);
  static const Color errorRed = Color(0xFFD11124);
}

/// --------------------
/// FONTS
/// --------------------
class AppFonts {
  // Font Sizes
  static const double h1 = 28.0;
  static const double h2 = 24.0;
  static const double h3 = 20.0;
  static const double h4 = 18.0;
  static const double body = 16.0;
  static const double small = 14.0;
  static const double tiny = 12.0;

  // Font Weights
  static const FontWeight light = FontWeight.w300;
  static const FontWeight regular = FontWeight.w400;
  static const FontWeight medium = FontWeight.w500;
  static const FontWeight semiBold = FontWeight.w600;
  static const FontWeight bold = FontWeight.w700;
}

/// --------------------
/// SIZES
/// --------------------
class AppSizes {
  // Icon Sizes
  static const double iconXS = 16.0;
  static const double iconSM = 20.0;
  static const double iconMD = 24.0;
  static const double iconLG = 32.0;

  // Spacing (4pt grid system)
  static const double spacingXS = 4.0;
  static const double spacingSM = 8.0;
  static const double spacingMD = 12.0;
  static const double spacingLG = 16.0;
  static const double spacingXL = 20.0;
  static const double spacingXXL = 24.0;

  // Border Radius
  static const double radiusSM = 4.0;
  static const double radiusMD = 6.0;
  static const double radiusLG = 8.0;

  // Elevation
  static const double elevationNone = 0.0;
  static const double elevationSM = 1.0;
  static const double elevationMD = 2.0;
}

/// --------------------
/// ROUTES
/// --------------------
class AppRoutes {
  static const String home = '/';
  static const String about = '/about';
}

/// --------------------
/// THEME
/// --------------------
class AppGlobalTheme {
  /// --------------------
  /// Default Global LightTheme
  /// --------------------
  static ThemeData lightTheme = ThemeData(
    brightness: Brightness.light,

    // Global Primary Color
    primaryColor: AppColors.primaryBlue,

    // Global Scaffold Background
    scaffoldBackgroundColor: Colors.white,

    // Global AppBar Style
    appBarTheme: const AppBarTheme(
      backgroundColor: AppColors.primaryBlue,
      foregroundColor: Colors.white,
      elevation: 0,
    ),

    // Global Color Scheme
    colorScheme: const ColorScheme.light(
      primary: AppColors.primaryBlue,
      secondary: AppColors.accentBlue,
      surface: Colors.white,
      onPrimary: Colors.white,
      onSecondary: Colors.white,
      onSurface: Colors.black87,
      error: AppColors.errorRed,
      onError: Colors.white,
    ),

    // Global ElevatedButton Default Style
    elevatedButtonTheme: ElevatedButtonThemeData(
      style: ElevatedButton.styleFrom(
        backgroundColor: AppColors.primaryBlue,
        foregroundColor: Colors.white,
        textStyle: const TextStyle(
          fontSize: AppFonts.body,
          fontWeight: AppFonts.medium,
        ),
        padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 12),
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.all(Radius.circular(AppSizes.radiusMD)),
        ),
      ),
    ),

    // Global OutlinedButton Default Style
    outlinedButtonTheme: OutlinedButtonThemeData(
      style: OutlinedButton.styleFrom(
        foregroundColor: AppColors.primaryBlue,
        side: const BorderSide(color: AppColors.primaryBlue, width: 1.5),
        textStyle: const TextStyle(
          fontSize: AppFonts.body,
          fontWeight: AppFonts.medium,
        ),
        shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.all(Radius.circular(AppSizes.radiusMD)),
        ),
      ),
    ),

    // Global TextButton Default Style
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        foregroundColor: AppColors.primaryBlue,
        textStyle: const TextStyle(
          fontSize: AppFonts.body,
          fontWeight: AppFonts.medium,
        ),
      ),
    ),

    // Global FAB Style
    floatingActionButtonTheme: const FloatingActionButtonThemeData(
      backgroundColor: AppColors.primaryBlue,
    ),

    // Global Text Theme
    textTheme: const TextTheme(
      headlineLarge: TextStyle(
        fontSize: AppFonts.h1,
        fontWeight: AppFonts.semiBold,
        color: Colors.black87,
      ),
      headlineMedium: TextStyle(
        fontSize: AppFonts.h2,
        fontWeight: AppFonts.bold,
        color: Colors.black87,
      ),
      titleLarge: TextStyle(
        fontSize: AppFonts.h3,
        fontWeight: AppFonts.medium,
        color: Colors.black87,
      ),
      bodyLarge: TextStyle(
        fontSize: AppFonts.body,
        fontWeight: AppFonts.regular,
        color: Colors.black87,
      ),
      bodySmall: TextStyle(
        fontSize: AppFonts.small,
        fontWeight: AppFonts.regular,
        color: Colors.black54,
      ),
    ),
  );
}

/// --------------------
/// APP ROOT
/// --------------------
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'LinkedIn Style App',
      debugShowCheckedModeBanner: false,
      theme: AppGlobalTheme.lightTheme,
      initialRoute: AppRoutes.home,
      routes: {
        AppRoutes.home: (context) => const HomeScreen(),
        AppRoutes.about: (context) => const AboutScreen(),
      },
    );
  }
}

/// --------------------
/// SCREENS
/// --------------------
class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Home")),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            // Uses Global ElevatedButtonTheme
            ElevatedButton(
              onPressed: () => Navigator.pushNamed(context, AppRoutes.about),
              child: const Text("Connect"),
            ),
            const SizedBox(height: 16),

            // Uses Global OutlinedButtonTheme
            OutlinedButton(onPressed: () {}, child: const Text("Message")),
            const SizedBox(height: 16),

            // Uses Global TextButtonTheme
            TextButton(onPressed: () {}, child: const Text("Follow")),
          ],
        ),
      ),
    );
  }
}

class AboutScreen extends StatelessWidget {
  const AboutScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("About")),
      body: const Center(child: Text("About Screen")),
    );
  }
}
