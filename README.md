public interface Vehiculo {
    double calcularVelocidad();
}

public class Automovil implements Vehiculo {

    private String marca;
    private double distancia;
    private double tiempo;

    public Automovil() {
        this.marca = "";
        this.distancia = 0;
        this.tiempo = 0;
    }

    public Automovil(String marca, double distancia, double tiempo) {
        this.marca = marca;
        this.distancia = distancia;
        this.tiempo = tiempo;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public double getDistancia() {
        return distancia;
    }

    public void setDistancia(double distancia) {
        this.distancia = distancia;
    }

    public double getTiempo() {
        return tiempo;
    }

    public void setTiempo(double tiempo) {
        this.tiempo = tiempo;
    }

    @Override
    public double calcularVelocidad() {
        if (tiempo == 0) return 0;
        return distancia / tiempo;
    }

    @Override
    public String toString() {
        return "Automovil{" +
                "marca='" + marca + '\'' +
                ", distancia=" + distancia +
                ", tiempo=" + tiempo +
                ", velocidad=" + calcularVelocidad() +
                " km/h}";
    }
}


public class Main {
    public static void main(String[] args) {

        Automovil auto1 = new Automovil("Toyota", 150, 3);

        auto1.setMarca("Honda");
        auto1.setDistancia(200);
        auto1.setTiempo(4);

        double velocidad = auto1.calcularVelocidad();
        System.out.println("Velocidad: " + velocidad + " km/h");

        System.out.println(auto1);
    }
}
