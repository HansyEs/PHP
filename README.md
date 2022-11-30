# PHP
### Obtener las fechas de inicio y final de la semana actual 
        $weekStartAt = strtotime('-' . date('w') . ' days');
        $weekEndAt   = date("Y-m-d", strtotime("+7 days", $weekStartAt));
### En ocasiones nos interesa redirigir un output del php hacia otro sitio, podemos hacerlo capturando la salida estándar y metiéndola luego en una variable que ya volcaremos a un archivo, por ejemplo o cualquier otra acción.
        ob_start();
        // Aquí irían las líneas con los echo necesarios...
        $resp = ob_get_contents(); 
        ob_end_clean();
### Retornar la letra de una columna del excel
        function get_letra_columna($col){
            $col--;
            $letras = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
            $primera_letra = '';
            if(intval($col / 26) != 0){
                $primera_letra = $letras[intval($col / 26)-1];
            }
            $segunda_letra = $letras[$col % 26];
            return trim($primera_letra . $segunda_letra);
        }
        // Uso
        echo get_letra_columna(75);
