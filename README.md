# Aktivitas-2
Praktikum PAB
class MainAppLayout extends StatefulWidget {
  const MainAppLayout({super.key});

  @override
  State<MainAppLayout> createState() => _MainAppLayoutState();
}

class _MainAppLayoutState extends State<MainAppLayout> {

  int _selectedIndex = 0;

  final List<Widget> _pages = [
    const KatalogScreen(),
    const BookingScreen(),
    const ProfileScreen(),
  ];

  @override
  Widget build(BuildContext context) {

    return Scaffold(
      backgroundColor: const Color(0xFFF2F2F2),

      body: Center(
        child: SingleChildScrollView(
          child: Padding(
            padding: const EdgeInsets.symmetric(
              vertical: 40,
              horizontal: 20,
            ),

            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              crossAxisAlignment: CrossAxisAlignment.center,

              children: [

                // CARD IDENTITAS
                Container(
                  width: 250,
                  height: 470,
                  padding: const EdgeInsets.all(15),

                  decoration: BoxDecoration(
                    color: const Color(0xFFF3F3F3),
                    border: Border.all(
                      color: const Color(0xFF555555),
                      width: 2,
                    ),
                    borderRadius: BorderRadius.circular(15),
                  ),

                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.center,
                    crossAxisAlignment: CrossAxisAlignment.center,

                    children: [

                      const SizedBox(height: 15),

                      const Text(
                        'Welcome to',
                        style: TextStyle(
                          fontSize: 18,
                          fontWeight: FontWeight.bold,
                        ),
                      ),

                      const Text(
                        'PRAKTIKUM PAB 2023',
                        style: TextStyle(
                          fontSize: 14,
                          color: Color(0xFF333333),
                        ),
                      ),

                      const SizedBox(height: 35),

                      const Text(
                        '1462300119',
                        style: TextStyle(
                          fontSize: 18,
                          fontWeight: FontWeight.bold,
                          color: Color(0xFF333333),
                        ),
                      ),

                      const SizedBox(height: 25),

                      ClipRRect(
                        borderRadius: BorderRadius.circular(8),

                        child: Image.asset(
                          'assets/gambar.png',
                          width: 130,
                          height: 130,
                          fit: BoxFit.cover,

                          errorBuilder: (context, error, stackTrace) {
                            return Container(
                              width: 130,
                              height: 130,
                              color: Colors.grey[300],
                              child: const Icon(
                                Icons.image_not_supported,
                                color: Colors.red,
                              ),
                            );
                          },
                        ),
                      ),

                      const SizedBox(height: 20),

                      const Text(
                        'M Daffa Ananta',
                        style: TextStyle(
                          fontSize: 20,
                          fontWeight: FontWeight.bold,
                          color: Color(0xFF111111),
                        ),
                      ),

                      const Spacer(),

                      ElevatedButton(
                        style: ElevatedButton.styleFrom(
                          backgroundColor: const Color(0xFF97E2AB),
                          minimumSize: const Size(150, 45),
                          shape: RoundedRectangleBorder(
                            borderRadius: BorderRadius.circular(15),
                          ),
                          elevation: 0,
                        ),

                        onPressed: () {},

                        child: const Text(
                          'Masuk',
                          style: TextStyle(
                            color: Colors.white,
                            fontSize: 18,
                            fontWeight: FontWeight.bold,
                          ),
                        ),
                      ),
                    ],
                  ),
                ),

                const SizedBox(height: 40),

                // APP TRAVELGO
                Container(
                  width: 340,
                  height: 560,

                  decoration: BoxDecoration(
                    color: Colors.white,
                    border: Border.all(
                      color: const Color(0xFFCCCCCC),
                      width: 2,
                    ),
                    borderRadius: BorderRadius.circular(15),
                  ),

                  child: ClipRRect(
                    borderRadius: BorderRadius.circular(13),

                    child: Column(
                      children: [

                        Expanded(
                          child: _pages[_selectedIndex],
                        ),

                        BottomNavigationBar(
                          currentIndex: _selectedIndex,

                          onTap: (index) {
                            setState(() {
                              _selectedIndex = index;
                            });
                          },

                          selectedItemColor: Colors.green,

                          items: const [

                            BottomNavigationBarItem(
                              icon: Icon(Icons.home),
                              label: 'Home',
                            ),

                            BottomNavigationBarItem(
                              icon: Icon(Icons.book_online),
                              label: 'Booking',
                            ),

                            BottomNavigationBarItem(
                              icon: Icon(Icons.person),
                              label: 'Profile',

Class  profilescreen

class ProfileScreen extends StatelessWidget {
  const ProfileScreen({super.key});

  @override
  Widget build(BuildContext context) {

    return const Scaffold(
      backgroundColor: Colors.white,

      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,

          children: [

            CircleAvatar(
              radius: 40,
              child: Icon(
                Icons.person,
                size: 40,
              ),
            ),

            SizedBox(height: 20),

            Text(
              'M Daffa Ananta',
              style: TextStyle(
                fontSize: 22,
                fontWeight: FontWeight.bold,
              ),
            ),

            SizedBox(height: 10),

            Text(
              '1462300119',
              style: TextStyle(
                fontSize: 18,
