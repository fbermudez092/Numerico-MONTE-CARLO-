# Numerico-MONTE-CARLO-
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%                                                   %%%%%%%%%%%%%%
%%%%%%%%%%%%%                       MONTE CARLO                 %%%%%%%%%%%%%%
%%%%%%%%%%%%%                                                   %%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%                                                                      %%%%%
%%%%%                       DEFINICIÓN DEL PROBLEMA:                       %%%%%
%%%%%    ¿Cuál es el valor esperado del volumen de un tetraedro formado    %%%%%     
%%%%%     por cuatro puntos elegido al azar dentro del tetraedro cuyos     %%%%%
%%%%%          vértices son (0,0,0), (0,1,0), (0,0,1) y (1,0,0)?           %%%%%     
%%%%%                (¡La respuesta exacta es desconocida!)                %%%%%
%%%%%                                                                      %%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%                                                                 %%%%%
%%%%%                         VALORES DE ENTRADA:                     %%%%%
%%%%% n: Es el número de veces que se hace el proceso de calcular     %%%%%     
%%%%%    el volumen de un tetraedro que cumpla las condiciones dadas  %%%%%
%%%%%    en la definición del problema.                               %%%%%   
%%%%%                                                                 %%%%%
%%%%%                         VALORES DE SALIDA:                      %%%%%
%%%%%            la función devuelve un vector [Volumen]              %%%%%     
%%%%% Volumen: es el promedio de todos los casos posibles que se      %%%%%
%%%%%          dieron para n repeticiones                             %%%%%   
%%%%%                                                                 %%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


function [Volumen] = MonteCarlo(n)
  if n<=0; %Verifica si el número de repeticiones es mayor que cero.
    error ('El numero de iteracciones tiene que ser mayor que cero');
  else
   casos=0;
   for k = 1:n
    x = rand;  %Genera los valores aleatorios.
    y = rand;
    z = rand;
    if x+y+z<1 %Verifica si cumple las condiciones del problema
      casos = casos +1;
    end
   end
   Volumen = casos / n; %Calcula los casos favorables entre casos posibles.
  end
end

