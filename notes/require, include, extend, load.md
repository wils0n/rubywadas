Include, extend, load, require
==============================

##Include 
Te permite insertar un modulo dentro de una clase, por ejm:

    module Log 
      def class_type
        "This class is of type: #{self.class}"
      end
    end
     
    class TestClass 
      include Log 
      # ... 
    end
     
    tc = TestClass.new.class_type

##Extend
Te permite agregar métodos del modulo **como métodos de la clase** y no como metodos de instancia (caso anterior), por ejm:

    module Log 
      def class_type
        "This class is of type: #{self.class}"
      end
    end
     
    class TestClass 
      extend Log 
      # ... 
    end
     
    tc = TestClass.class_type
    
##Load
Te permite cargar una libreria mas de una vez  
Usar el nombre de la libreria mas la extensión *.rb*

#Nota
Usualmente los 2 últimos métodos se usan para cargar una libreria de un archivo diferente.