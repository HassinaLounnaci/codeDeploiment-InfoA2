# Implémentation de RMI en Java

**Interface distante :**

```java
import java.rmi.*;

public interface Hello extends Remote {
    String sayHello(String name) throws RemoteException;
}
```

**Implémentation de l'objet :**

```java
import java.rmi.server.*;
import java.rmi.*;

public class HelloImpl extends UnicastRemoteObject implements Hello {
    public HelloImpl() throws RemoteException {}
    public String sayHello(String name) {
        return "Bonjour " + name + "!";
    }
}
```

RMI est une technologie qui permet d'accéder aux méthodes d'un objet à partir d'une machine distante, en utilisant une référence de l'objet. RMI simplifie le code en gérant toute la partie réseau (passage de notre appel dans le réseau).

Dans le morceau de code ci-dessus, on a défini une interface (pas d'instanciation) contenant une seule méthode (`sayHello`), qu'on a implémentée ensuite dans la classe `HelloImpl`.
