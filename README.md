## Taller3

##Pesentado por: Daniela Jaramillo Solar y Jesus Goyeneche Hernandez 
##Calculo de factura de energía eléctrica



## ALGORITMO
Calculo de la factura de energia electrica

1. Iniciar
2. Declarar variables: consumo, costo_kWh, estrato (1-6), altitud, total_a_pagar, subsidio_contribucion, consumo_basico
3. Obtener el consumo en kWh.
4. Obtener el costo por kWh en pesos colombianos.
5. Obtener el estrato socioeconómico.
6. Obtener la altitud en metros sobre el nivel del mar.
7. Determinar el consumo básico según la altitud:
  Si la altitud es menor a 1000 metros, el consumo básico es 173 kWh.
  Si la altitud es mayor o igual a 1000 metros, el consumo básico es 130 kWh.
8. Calcular el costo total sin subsidios ni contribuciones: total a pagar = consumo * costo_kwh.
9. Aplicar el subsidio o contribución según el estrato:
  Si el estrato es 1 se aplica subsidio del 60% sobre el consumo básico.
  Si el estrato es 2 se aplica subsidio del 50% sobre el consumo básico.
  Si el estrato es 3 se aplica subsidio del 15% sobre el consumo básico.
  Si el estrato es 4 no se aplica subsidio ni contribución.
  Si el estrato es si 5 y 6 se aplica contribución del 20% sobre todo el consumo.
  Si el estrato es comercial se aplica contribución del 20% sobre todo el consumo.
10. Mostrar el total a pagar.
11. Finalizar

## PSEUDOCÓDIGO
# CALCULO_FACTURA_ENERGIA_ELECTRICA
Start
Declare float consumo
Declare float costo_kWh
Declare int estrato
Declare float altitud  
Declare float total_a_pagar
Declare float subsidio_contribucion
Declare float consumo_basico

Display "Cantidad de energía consumida en kWh"
Input consumo
Display "Costo del kWh en el mes respectivo en COP"
Input costo_kWh
Display "Estrato socioeconómico del usuario de (1 a 6)"
Input estrato
Display "Ingrese la altitud en metros sobre el nivel del mar"
Input altitud

## Determinar el consumo básico según la altitud

if (altitud <= 1000) then
    consumo_basico = 173
else if (altitud >= 1000)
    consumo_basico = 130
end
Set total_a_pagar sin contribucion ni subsidio = consumo * costo_kwh

## Aplicar subsidio o contribución según el estrato

if (estrato == 1) then
    if (consumo <= consumo_basico) then
        subsidio_contribucion = total_a_pagar * 0.60
    if else
        subsidio_contribucion = consumo_basico * costo_kwh * 0.60
    end if
    total_a_pagar = total_a_pagar - subsidio_contribucion
else if (estrato == 2) then
    if (consumo <= consumo_basico) then
        subsidio_contribucion = total_a_pagar * 0.50
    if else
        subsidio_contribucion = consumo_basico * costo_kwh * 0.50
    end if
    total_a_pagar = total_a_pagar - subsidio_contribucion
else if (estrato == 3) then
    if (consumo <= consumo_basico) then
        subsidio_contribucion = total_a_pagar * 0.15
    if else
        subsidio_contribucion = consumo_basico * costo_kwh * 0.15
    end if
    total_a_pagar = total_a_pagar - subsidio_contribucion
else if (estrato == 5 o estrato == 6) then
    subsidio_contribucion = total_a_pagar * 0.20
    total_a_pagar = total_a_pagar + subsidio_contribucion
end if

Display "El total a pagar es: ", total_a_pagar, " COP"

End

## CODIGO PYTHON
# Declarar variables
consumo = float(input("Cantidad de energía consumida en kWh: "))
costo_kWh = float(input("Costo del kWh en el mes respectivo en COP: "))
estrato = int(input("Estrato socioeconómico del usuario (1 a 6): "))
altitud = float(input("Ingrese la altitud en metros sobre el nivel del mar: "))

# Determinar el consumo básico según la altitud
if altitud < 1000:
    consumo_basico = 173
else:
    consumo_basico = 130

# Calcular el costo total sin contribución ni subsidio
total_a_pagar = consumo * costo_kWh

# Aplicar subsidio o contribución según el estrato
if estrato == 1:
    if consumo <= consumo_basico:
        subsidio_contribucion = total_a_pagar * 0.60
    else:
        subsidio_contribucion = consumo_basico * costo_kWh * 0.60
    total_a_pagar -= subsidio_contribucion

elif estrato == 2:
    if consumo <= consumo_basico:
        subsidio_contribucion = total_a_pagar * 0.50
    else:
        subsidio_contribucion = consumo_basico * costo_kWh * 0.50
    total_a_pagar -= subsidio_contribucion

elif estrato == 3:
    if consumo <= consumo_basico:
        subsidio_contribucion = total_a_pagar * 0.15
    else:
        subsidio_contribucion = consumo_basico * costo_kWh * 0.15
    total_a_pagar -= subsidio_contribucion

elif estrato == 5 or estrato == 6:
    contribucion = total_a_pagar * 0.20
    total_a_pagar += contribucion

# Mostrar el total a pagar
print(f"El total a pagar es: {total_a_pagar:.2f} COP")
