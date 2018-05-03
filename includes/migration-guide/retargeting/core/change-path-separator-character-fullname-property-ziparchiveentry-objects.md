### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Alteração no caractere separador de caminho na propriedade FullName de objetos ZipArchiveEntry

|   |   |
|---|---|
|Detalhes|Em aplicativos destinados ao .NET Framework 4.6.1 e versões posteriores, o caractere separador do caminho foi alterado de uma barra invertida (&quot;&quot;) para uma barra (&quot;/&quot;) na propriedade <xref:System.IO.Compression.ZipArchiveEntry.FullName> de objetos <xref:System.IO.Compression.ZipArchiveEntry> criados por sobrecargas do método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>. A alteração deixa a implementação do .NET em conformidade com a seção 4.4.17.1 da [Especificação de Formato de Arquivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e permite que arquivos .ZIP sejam descompactados em sistemas diferentes do Windows. Descompactar um arquivo zip criado por um aplicativo destinado a uma versão anterior do .NET Framework em sistemas operacionais diferentes do Windows, como Macintosh, não preserva a estrutura de diretórios. Por exemplo, no Macintosh, ela cria um conjunto de arquivos cujo nome de arquivo concatena o caminho do diretório com qualquer caractere de barra invertida (&quot;&quot;) e o nome do arquivo. Consequentemente, a estrutura do diretório de arquivos descompactados não é preservada.|
|Sugestão|O impacto dessa alteração em arquivos .ZIP que são descompactados no sistema operacional Windows por APIs no namespace <xref:System.IO?displayProperty=nameWithType> do .NET Framework deve ser mínimo, uma vez que as APIs podem lidar perfeitamente com uma barra (&quot;/&quot;) ou uma barra invertida (&quot;\&quot;) como o caractere separador de caminho. Se essa alteração não for desejável, será possível recusá-la adicionando uma definição de configuração à seção [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) do arquivo de configuração de aplicativo. O exemplo a seguir mostra a seção `<runtime>` e a opção de recusa `Switch.System.IO.Compression.ZipFile.UseBackslash`:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Além disso, os aplicativos destinados a versões anteriores do .NET Framework, mas estão sendo executados no .NET Framework 4.6.1 e versões posteriores, podem aceitar esse comportamento adicionando uma definição de configuração à seção [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) do arquivo de configuração de aplicativo. Veja a seguir a seção `<runtime>` e a opção de aceitação `Switch.System.IO.Compression.ZipFile.UseBackslash`.<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Escopo|Microsoft Edge|
|Versão|4.6.1|
|Tipo|Redirecionando|
|APIs afetadas|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|
