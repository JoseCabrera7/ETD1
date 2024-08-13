# Estructuras de Datos 1
# PROGRAMADORES: JOSE CABRERA - JUAN JARAMILLO

    public String metodo2( )
    {
    	try {
     
    		generarReporteDiscosCostosos();
    		return ("Reporte Generado Exitosamente!!");
    	}
    	catch(Exception e) {
    		return ("Error al generar el reporte, tipo: "+e);
      }
      
      }
      public void generarReporteDiscosCostosos() throws FileNotFoundException{

    	File miArchivo = new File("./data/discosCostosos");
    	PrintWriter pluma = new PrintWriter(miArchivo);
    	pluma.println("----Reporte de Canciones de alto Costo----");
    	pluma.println("--------------------------------");
    	
    	
    	for (int i = 0; i < discos.size(); i++) {
    			
			Disco miDisco = (Disco)discos.get(i);
			if (miDisco.darPrecioDisco()>3500&&miDisco.darGenero().equals("Rock")||miDisco.darGenero().equals("Pop")) {
				pluma.println("-----------Discos Costosos------------");
				pluma.println("Nombre:" + miDisco.darNombreDisco() + "Artista: "+miDisco.darArtista() + 
			    		"Género: "+miDisco.darGenero() + " Precio: "+miDisco.darPrecioDisco());
			}
			else if (miDisco.darPrecioDisco()<3500&&miDisco.darGenero().equals("Rock")||miDisco.darGenero().equals("Pop")){
				pluma.println("El disco:" + miDisco.darNombreDisco() + " no es costoso, su valor es de: "+ miDisco.darPrecioDisco());
			}
    		
    	}
    	pluma.close(); }


    
