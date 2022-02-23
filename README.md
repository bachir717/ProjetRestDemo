# ProjetRestDemo

http://localhost:8080/demorestfullws/rest/hello/xyz


1) http://localhost:8080 : entrée dans le serveur d'application

2) demorestfullws : application qui va gérer la requête

3) rest/ : solliciter Jersey (la servlet com.sun.jersey.spi.container.servlet.ServletContainer)

4) Jersey a besoin de savoir où sont les classes de traitement de la reqûete
--> paramètre com.sun.jersey.config.property.packages  de la Servlet

<init-param>
		     <param-name>com.sun.jersey.config.property.packages</param-name>
		     <param-value>com.objis.demorest</param-value>
		</init-param>

Dans ce projet il n'y a qu'un classe.

5) / hello/

Parmi les classes élligibles, seule la classe HelloService  supporte l'url hello/	

@Path("/hello")

6) /xyz

Parmi les méthodes de la classe HelloServic, seule la méthode getMsg() gère /xyz

--> le code de la méthode getMsg est exécuté.

Il pourrait solliciter un couche DAO...

la méthode possède un paramètre qui est la chaine xyz qui peut donc être exploitée par le développeur.

7)

return Response.status(200).entity(output).build();

status(200) : le serveur a bien reçu la requête et sait répondre.

entity(output).build() : Gènère une page HTML avec comme contenu le 'output'
