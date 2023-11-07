

/* 
* Classe que implementa a interface 'map'.
*/
 import java.util.HashMap; 


/*
* Interface com metodos para adicionar, remover e recuperar elementos com base em suas chaves.
*/
import java.util.Map; 


/**
* Classe que simula um banco de dados 
*/
public class LoginScreen {
	private Map<String, String> userDatabase; // simula um banco de dados, passando o nome e o usuario.
	
/**
* Construtor de LoginScreen, faz a instancia e inicializa o banco de dados.
* Para exemplificar, ha 2 exemplos de nome e senha dos usuarios sendo inseridos.
*/
	public LoginScreen() {
		userDatabase = new HashMap<>();
		userDatabase.put("john", "password123");	
		userDatabase.put("alice", "securepass");		
	}

/**
* Autenticacao de um usuario baseado no seu nome e na senha.
*
* @param username o nome que usuario inserir para tentar logar.
* @param password a senha que do usuario.
* @return {@code true} se a autenticacao for bem sucedida, {@code false} caso contrario.
*/
	public boolean login(String username, String password) {
		
		if (userDatabase.containsKey(username)) {
			String storedPassword = userDatabase.get(username);
			if (storedPassword.equals(password)) {
				return true; // Sucesso na autenticacao 
			}
		
		}
		return false; // Autenticacao falhou
	}


/**
* Adiciona um novo usuario ao banco de dados. Note que este metodo nao
* e recomendado para o uso em um ambiente de producao, pois carece 
* de medidas de seguranca adequadas.
*
* @param username representa o nome de um novo usuario
* @param password representa a senha de um novo usuario
*/
public void addUser(String username, String password) {
		userDatabase.put(username, password);
	}
	
}


