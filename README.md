# Cuenta-atras-java

~~~
public void crono_atras() throws InterruptedException {
        int min, sec, hora;
        System.out.println("Introduce cuando quieres empezar la cuenta atras:");
        hora = leerInt("Horas: ");
        min = leerInt("Minutos: ");
        sec = leerInt("Segundos: ");

        //gestion de errores
        while (sec > 60) {
            min++;
            sec = sec - 60;
        }
        while (min > 60) {
            hora++;
            min = min - 60;
        }

        while (!(hora == 0 && min == 0 && sec == 0)) {
            //mostrar por pantalla
            if (hora < 10) {
                System.out.print("0" + hora);
            } else {
                System.out.println(hora);
            }
            System.out.print(":");

            if (min < 10) {
                System.out.print("0" + min);
            } else {
                System.out.print(min);
            }
            System.out.print(":");
            if (sec < 10) {
                System.out.print("0" + sec);
            } else {
                System.out.print(sec);
            }

            System.out.println("");

            //calculos
            if (sec == 0) {
                if (min == 0) {
                    hora--;
                    min = 59;
                    sec = 59;
                } else if (min != 0) {
                    min--;
                    sec = 59;
                }
            } else {
                sec--;
            }

            Thread.sleep(1000);
        }
        System.out.println("00:00:00");
        System.out.println("BOOM");

    }

    public int leerInt(String msg) {
        System.out.print(msg);
        int x = lt.nextInt();
        return x;
    }
~~~
