import java.util.Random;
import java.util.Scanner;

public class game_tongkat {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Random random = new Random();

        // Tentukan siapa yang mulai duluan
        boolean playerTurn = random.nextBoolean();

        // Generate jumlah tongkat antara 10-30, dan manipulasi agar mod 4 == 1
        int tongkat = random.nextInt(21) + 10; // antara 10 - 30
        int sisa = tongkat % 4;
        if (sisa != 1) {
            tongkat += (1 - sisa + 4) % 4; // manipulasi agar tongkat % 4 == 1
        }

        System.out.println("Jumlah tongkat awal: " + tongkat);
        System.out.println(playerTurn ? "Kamu main pertama." : "Komputer main pertama.");

        // Game loop
        while (tongkat > 0) {
            System.out.println("\nSisa tongkat: " + tongkat);

            if (playerTurn) {
                int ambil;
                do {
                    System.out.print("Ambil 1, 2, atau 3 tongkat: ");
                    ambil = input.nextInt();
                } while (ambil < 1 || ambil > 3 || ambil > tongkat);

                tongkat -= ambil;
            } else {
                int ambilKomputer = (tongkat - 1) % 4;
                if (ambilKomputer == 0 || ambilKomputer > 3) ambilKomputer = 1; // fallback
                ambilKomputer = Math.min(ambilKomputer, tongkat);

                System.out.println("Komputer mengambil: " + ambilKomputer);
                tongkat -= ambilKomputer;
            }

            if (tongkat == 0) {
                if (playerTurn) {
                    System.out.println("Kamu mengambil tongkat terakhir. Kamu kalah!");
                } else {
                    System.out.println("Komputer mengambil tongkat terakhir. Komputer kalah!");
                }
                break;
            }

            playerTurn = !playerTurn;
        }

        input.close();
    }
}
