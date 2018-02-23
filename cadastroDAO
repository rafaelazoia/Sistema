public class FornecedoresDAO {
	public void salvar(Fornecedores f) throws SQLException {
		StringBuilder sql = new StringBuilder();
		sql.append("INSERT INTO fornecedores ");
		sql.append("(nome) ");
		sql.append("VALUES (?)");

		Connection conexao = ConexaoBD.conectar();

		PreparedStatement comando = conexao.prepareStatement(sql.toString());
		comando.setString(1, f.getDescricao());
		comando.executeUpdate();

	}

	public void excluir(Fornecedores f) throws SQLException {
		StringBuilder sql = new StringBuilder();
		sql.append("DELETE FROM fornecedores ");
		sql.append("WHERE codigo = ? ");

		Connection conexao = ConexaoBD.conectar();

		PreparedStatement comando = conexao.prepareStatement(sql.toString());
		comando.setLong(1, f.getCodigo());
		comando.executeUpdate();

	}

	public void editar(Fornecedores f) throws SQLException {
		StringBuilder sql = new StringBuilder();
		sql.append("UPDATE fornecedores ");
		sql.append("SET nome = ? ");
		sql.append("WHERE codigo = ? ");

		Connection conexao = ConexaoBD.conectar();

		PreparedStatement comando = conexao.prepareStatement(sql.toString());
		comando.setString(1, f.getNome());
		comando.setLong(2, f.getCodigo());
		comando.executeUpdate();

	}
  public ArrayList<Fornecedores> listar() throws SQLException {
		StringBuilder sql = new StringBuilder();
		sql.append("SELECT codigo, nome ");
		sql.append("FROM fornecedores ");
		sql.append("ORDER BY nome ASC");

		Connection conexao = ConexaoBD.conectar();

		PreparedStatement comando = conexao.prepareStatement(sql.toString());

		ResultSet resultado = comando.executeQuery();
		ArrayList<Fornecedores> lista = new ArrayList<Fornecedores>();

		while (resultado.next()) {
			Fornecedores f = new Fornecedores();
			f.setCodigo(resultado.getLong("codigo"));
			f.setDescricao(resultado.getString("nome"));

			lista.add(f);
		}

		return lista;

	}
 }
