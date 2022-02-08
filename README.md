# 378.-Gerenciadores-de-Layout
Alternando cores e valores
CAIXA
______________________________
public class Caixa extends HBox {

	private static int i = 0;
	private String[] cores = {
			"#c33c5e", "39aac6", "#28d79a",
			"#fb750e", "#6667a8", "#f9060e"			
	};
	public Caixa() {
		this(100, 100);
	}
	public Caixa(int largura, int altura) {
		setAlignment(Pos.CENTER);
		
		setMinWidth(largura);
		setMinHeight(altura);
		
		BackgroundFill fill = new BackgroundFill(Color.web(cores[i]), CornerRadii.EMPTY, Insets.EMPTY);
		setBackground(new Background(fill));
		
		i++;
		if(i == 6) i = 0;
	}
	
	public Caixa comTexto(String texto) {
		Label label = new Label(texto);
		label.setFont(new Font(24));
		getChildren().add(label);
		return this;
	}
}
LAYOUT
____________________________________
public class AppLayout extends Application{
		
	@Override
	public void start(Stage primaryStage) throws Exception {
		
		VBox temp = new VBox();
		temp.getChildren().add(new Caixa().comTexto("1"));
		temp.getChildren().add(new Caixa().comTexto("2"));
		temp.getChildren().add(new Caixa().comTexto("3"));
		temp.getChildren().add(new Caixa().comTexto("4"));
		temp.getChildren().add(new Caixa().comTexto("5"));
		temp.getChildren().add(new Caixa().comTexto("6"));
		temp.getChildren().add(new Caixa().comTexto("7"));
		temp.getChildren().add(new Caixa().comTexto("8"));
		
		Scene principal = new Scene(temp, 800, 600);

		primaryStage.setScene(principal);
		primaryStage.setTitle("Gerenciadores de Layout");
		primaryStage.show();		
	}
	public static void main(String[] args) {
		launch(args);
	}
}
![image](https://user-images.githubusercontent.com/95525963/153090093-23467c51-63fd-4e99-b479-6bb64e920ec4.png)


