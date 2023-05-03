# Practica2LDP
Práctica 2 Lenguajes de Programación 
Estefanía Ramirez y Rafael David Palau

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.math.BigDecimal;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.List;
import java.util.regex.Pattern;
import java.util.stream.Collectors;

public class importacionCsv {
    public List<Ventas> cargarVentas(sales_data.csv) throws IOException, ParseException {
        Pattern pattern = Pattern.compile(",");
        BufferedReader br = new BufferedReader(new FileReader(sales_data.csv));
        List<Ventas> ventas = br.lines().skip(1)
                .map(line -> {
                    String[] campos = pattern.split(line);
                    Ventas venta = new Ventas();
                    venta.setOrderNumber(Integer.parseInt(campos[0]));
                    venta.setQuantityOrdered(Integer.parseInt(campos[1]));
                    venta.setPriceEach(new BigDecimal(campos[2]));
                    venta.setOrderLineNumber(Integer.parseInt(campos[3]));
                    venta.setSales(new BigDecimal(campos[4]));
                    venta.setOrderDate(new SimpleDateFormat("M/d/yyyy").parse(campos[5]));
                    venta.setStatus(campos[6]);
                    venta.setQtrId(Integer.parseInt(campos[7]));
                    venta.setMonthId(Integer.parseInt(campos[8]));
                    venta.setYearId(Integer.parseInt(campos[9]));
                    venta.setProductLine(campos[10]);
                    venta.setMsrp(new BigDecimal(campos[11]));
                    venta.setProductCode(campos[12]);
                    venta.setCustomerName(campos[13]);
                    venta.setPhone(campos[14]);
                    venta.setAddressLine1(campos[15]);
                    venta.setAddressLine2(campos[16]);
                    venta.setCity(campos[17]);
                    venta.setState(campos[18]);
                    venta.setPostalCode(campos[19]);
                    venta.setCountry(campos[20]);
                    venta.setTerritory(campos[21]);
                    venta.setContactLastName(campos[22]);
                    venta.setContactFirstName(campos[23]);
                    venta.setDealSize(campos[24]);
                    return venta;
                })
                .collect(Collectors.toList());
        br.close();
        return ventas;
    }
}
public class Main{
    public static void main(String [] args) throws Exception{
  
            List<Ventas> ventasNY = ventas.stream()
            .filter(venta -> venta.getCiudad().equals("New York"))
            .collect(Collectors.toList());

            double totalNY = ventasNY.stream() 
            .mapToDouble(Ventas::getSales)
            .sum(); 

            long autoClasicoNY = ventasNy.stream()
            .filter(venta->venta.getProductionLine().equals("Classic Cars"))
            .count

            long motocicletasNY = ventasNY.stream()
            .filter(venta->venta.getProductionLine().equals("Motorcycles"))
            .count();

            double totalMotocicletasNY = ventasNY.stream()
            .filter(venta->venta.getProductionLine().equals("Motorcycles"))
            .mapToDouble(Ventas::getSales)
            .sum();

            Ventas clienteMasAutos = ventas.stream()
            

          Ventas minCliente = ventas.stream()
          
        }
    }
