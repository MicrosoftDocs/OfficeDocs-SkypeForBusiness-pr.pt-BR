---
title: Implantar Servidores de Borda no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Resumo: Saiba como implantar servidores de borda em sua Skype para ambiente de negócios Server 2015.'
ms.openlocfilehash: ec69655ad5a614e9a2a22e82b7c1e56eed52102b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-servers-in-skype-for-business-server-2015"></a>Implantar Servidores de Borda no Skype for Business Server 2015
 
**Resumo:** Aprenda a implantar servidores de borda em sua Skype para ambiente de negócios Server 2015.
  
As seções a seguir contêm etapas que devem ser seguidas após o Skype para obter a documentação Business Server 2015 [Planejar para implantações de servidor de borda em Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) foi analisada. As etapas da implantação são:
  
- Interfaces de Rede
    
- Instalação
    
- Certificados
    
- Iniciando os servidores de borda
    
## <a name="network-interfaces"></a>Interfaces de Rede

Conforme observado em Planning, você estará seja configurando sua interface de rede com o DNS na rede de perímetro que hospeda os servidores de borda ou sem o DNS na rede de perímetro.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuração da interface com os servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada servidor de borda, um para a interface interna e outro para a interface externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Na sua interface externa, você vai configurar **um** dos seguintes procedimentos:
    
   a. Três endereços IP estáticos na sub-rede da rede externa de perímetro e, em seguida, aponte o gateway padrão à interface interna do firewall externo. Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS de perímetro.
    
   b. Um endereço IP estático na sub-rede da rede externa de perímetro e, em seguida, aponte o gateway padrão à interface interna do firewall externo. Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS de perímetro. Essa configuração só é aceitável se você tiver configurado anteriormente sua topologia para valores não-padrão nas atribuições de portas, que é abordada no artigo [criar sua topologia de borda para Skype para Business Server 2015](create-your-edge-topology.md) .
    
3. Na interface interna, configure um IP estático na sub-rede da rede de perímetro interno e não definir um gateway padrão. Defina as configurações do DNS do adaptador a fim de apontar para pelo menos um servidor DNS, preferencialmente um par de servidores DNS de perímetro.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas onde residem os clientes, Skype para Business Server 2015 e servidores do Exchange Unified Messaging (UM).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuração da interface sem os servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada servidor de borda, um para a interface interna e outro para a interface externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Na sua interface externa, você vai configurar **um** dos seguintes procedimentos:
    
   a. Três endereços IP estáticos na sub-rede da rede externa de perímetro. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definindo o roteador voltado à internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS do adaptador a fim de apontar para um servidor de DNS externo, preferencialmente um par de servidores DNS externos.
    
   b. Um endereço IP estático na sub-rede da rede externa de perímetro. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definindo o roteador voltado à internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS do adaptador a fim de apontar para um servidor DNS externo, ou preferencialmente para um par de servidores DNS externos. Essa configuração só é aceitável se você tiver configurado anteriormente sua topologia para valores não-padrão nas atribuições de portas, que é abordada no artigo [criar sua topologia de borda para Skype para Business Server 2015](create-your-edge-topology.md) .
    
3. Na interface interna, configure um IP estático na sub-rede da rede de perímetro interno e não definir um gateway padrão. Deixe as configurações DNS do adaptador vazias.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas onde residem os clientes, Skype para Business Server 2015 e servidores do Exchange Unified Messaging (UM).
    
5. Edite o arquivo HOST em cada servidor de borda para conter um registro para o servidor de próximo salto ou IP virtual (VIP). Esse registro será o diretor, servidor Standard Edition ou pool de Front-End que você configurou como o endereço de salto seguinte do servidor de borda no construtor de topologia. Se você estiver usando o balanceamento de carga DNS, inclua uma linha de cada membro do pool de próximo salto.
    
## <a name="installation"></a>Instalação

Para concluir estas etapas com êxito, você precisará ter seguido as etapas no artigo [criar sua topologia de borda para Skype para Business Server 2015](create-your-edge-topology.md) .
  
1. Faça logon no servidor que você tiver sido configurando para a função de servidor de borda com uma conta que está no grupo de administradores locais.
    
2. Você precisará o arquivo de configuração de topologia que você copiou o check-out no final da documentação de topologia de servidor de borda nesta máquina. Acesse a mídia externa na qual você colocou o arquivo de configuração (como uma unidade USB ou compartilhamento).
    
3. Inicie o **Assistente para implantação**.
    
4. Depois que o assistente for aberto, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**.
    
5. O assistente será executado verificações para ver se nada já está instalado. Como esta é a primeira vez em que executar o assistente, você vai querer iniciar em **etapa 1. Instalar repositório de configuração Local.**
    
6. A caixa de diálogo **Configurar réplica Local do gerenciamento Central armazenar** será exibida. Você precisará clique em **Importar de um arquivo (recomendado para servidores de borda)**.
    
7. A partir daqui, navegue para a localização da topologia que você exportou anteriormente, selecione o arquivo .zip, clique em **Abrir**e clique em **Avançar**.
    
8. O Assistente de implantação ler o arquivo de configuração e gravar o arquivo de configuração XML no computador local.
    
9. Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.
    
10. No Assistente de implantação, clique em **etapa 2. Instalar ou remover Skype para componentes de servidor de negócios**. Em seguida, o assistente instalará o Skype Business Server 2015 para componentes de borda especificado no arquivo de configuração XML que foi armazenado no computador local.
    
11. Depois que a instalação 's completa, você pode mover para as etapas na seção **certificados** abaixo.
    
## <a name="certificates"></a>Certificados

Requisitos de certificado para o servidor de borda podem ser encontrados na documentação de planejamento de certificado de borda. As etapas para configurar os certificados estão indicadas abaixo.
  
> [!NOTE]
> Ao executar o Assistente de certificado, você precisa estar logado como uma conta com as permissões corretas para o tipo de modelo de certificado que você vai usar. Por padrão, um Skype para solicitação de certificado de servidor de negócios irá usar o modelo de certificado de servidor Web. Se você está conectado com uma conta que seja membro do grupo RTCUniversalServerAdmins para solicitar um certificado via esse modelo, verifique novamente para se certificar de que o grupo foi atribuído as permissões de registrar para usar esse modelo. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de Interface de Borda Interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Faça download ou exportar a cadeia de certificação

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;um. Fazer o download usando o site da web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eu. Faça logon em um Skype para Business Server 2015 server em sua rede interna como membro do grupo Administradores local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Abra o backup **Iniciar**e **execute** (ou **pesquisa** e **execute** ) e, em seguida, digite o seguinte:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por exemplo:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Na página de web certsrv da AC emissora, em **Selecionar uma tarefa**, clique em **baixar um certificado de autoridade de certificação, cadeia de certificados ou lista de certificados Revogados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Em  **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**, clique em  **Fazer download de cadeia de certificados de autoridade de certificação**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Na caixa de diálogo  **Download de Arquivo**, clique em  **Salvar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salve o arquivo. p7b no disco rígido do servidor e copie-o para uma pasta em cada um dos seus servidores de borda.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportar usando MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eu. Você pode exportar o certificado raiz da AC de qualquer máquina associada ao domínio, usando o MMC. Ir para **Iniciar** e **Executar**, ou abrir **Pesquisa**, e digite **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. No console MMC (Console de Gerenciamento Microsoft), clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Na lista de diálogos **Adicionar ou Remover Snap-ins**, selecione **Certificados**, e depois clique em **Adicionar**. Ao ser solicitado, selecione **Conta do Computador**, e depois clicar em **Avançar**. Na caixa de diálogo **Selecionar Computador**, selecione **Computador Local**. Clique em **Concluir**, e depois em **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Expanda **certificados (computador Local)**. Expanda **autoridades de certificação raiz confiáveis**. Selecione **certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Clique no certificado raiz emitido por sua AC. Clique com o botão direito no certificado, escolha **Todas as Tarefas** no menu, e selecione **Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. O **Assistente de Exportação de Certificado** será aberto. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. Na caixa de diálogo **Exportar o Formato do Arquivo**, escolha o formato que deseja exportar. Nossa recomendação é **Cryptographic Message Syntax Standard - PKCS #7 Certificados (P7b)**. Se isso for sua escolha, bem, lembre-se também selecionar a caixa de seleção **incluir todos os certificados no caminho de certificação se possível** , como também exportará a cadeia de certificados, inclusive o certificado de autoridade de certificação raiz e todos os certificados intermediários. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii. Na caixa de diálogo **Arquivo para exportar**, na entrada do nome do arquivo, digite um caminho e o nome de arquivo (a extensão padrão seria .p7b) para o certificado exportado. Se é mais fácil sobre você, escolha o botão **Procurar** para ir até o local em que você deseja salvar o certificado exportado para e nomeie o certificado exportado aqui. Clique em **Salvar**e em seguida **Avançar** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Revise o resumo de suas ações e clique em **Concluir** para concluir a exportação do certificado. Clique em **OK** para confirmar que a exportação foi bem sucedida.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copie o arquivo. p7b para cada um dos seus servidores de borda.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importar a cadeia de certificação

&nbsp;&nbsp;&nbsp;um. Em cada servidor de borda, abra o MMC (escolha **Iniciar** e **execute**ou **pesquisa**e digite **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;b. No menu **Arquivo**, clique em  **Adicionar/Remover Snap-in**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;c. Na caixa de diálogo **Adicionar ou Remover Snap-ins**, clique em  **Certificados**e, em seguida, clique em  **Adicionar**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa de diálogo **Selecionar computador**, certifique-se de que a opção **Computador local: (o computador em que este console está sendo executado)** esteja marcada e clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;f. Clique em **Fechar**e, em seguida, clicar em **OK**.
    
&nbsp;&nbsp;&nbsp;g. Na árvore do console, expanda **Certificados (computador local)**, clique com o botão direito do mouse em **Autoridades de Certificação Raiz Confiáveis**, vá para  **Todas as tarefas**e clique em **Importar**.
    
&nbsp;&nbsp;&nbsp;h. No assistente exibido, na caixa de texto **Arquivo a ser importado**, especifique o nome do arquivo do certificado (o nome dado ao arquivo .p7b na seção anterior). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;Eu. Deixe o botão de opção em **Colocar todos os certificados no repositório a seguir, como Autoridades de Certificação Raiz Confiáveis** devem ser selecionados. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;j. Revise o resumo e clique em **Concluir** para terminar a importação.
    
&nbsp;&nbsp;&nbsp;k. Isso precisa ser feito para cada servidor de borda que você estiver implantando.
    
### <a name="3-create-the-certificate-request"></a>3. criar a solicitação de certificado

&nbsp;&nbsp;&nbsp;um. Faça logon em um dos seus servidores de borda, inicie o Assistente de implantação e em **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **Executar** (ou **Executar novamente**, se você já executou este assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Solicitação de Certificado**, certifique-se que **Certificado da Borda Interna** está selecionado e clique em **Solicitação**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Solicitações Atrasadas ou Imediatas**, escolha **Enviar a solicitação imediatamente para uma autoridade de certificação online** se você tiver acesso a um ambiente da Borda, ou caso contrário, escolha **Preparar a solicitação agora, mas enviá-la  Posteriormente**.
    
&nbsp;&nbsp;&nbsp;d. Na página **Arquivo de Solicitação de Certificado**, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert cer). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na página  **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo padrão do Servidor da Web, marque a caixa de seleção **Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada**. Caso contrário, não continue com os procedimentos.
    
&nbsp;&nbsp;&nbsp;f. Na página  Nome e Configurações de Segurança, siga estes procedimentos:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eu. Em **Nome amigável**, digite um nome de exibição para o certificado (por exemplo, Borda Interna).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Em **Comprimento de bit**, escolha a comprimento de bit (o padrão é 2048, você pode aumentar e ter mais segurança, mas causará diminuição no desempenho).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Se você precisa de um certificado exportável, você deve marcar a caixa de seleção **Marcar chave privada de certificado como exportável**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;g. Na página **Informações da Organização**, insira o nome para sua organização e unidade organizacional (UO). É possível inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;h. Na página  **Informações Geográficas**, insira as informações de localização.
    
&nbsp;&nbsp;&nbsp;Eu. Na página **Nome de Entidade/Nomes alternativos de Entidades**, isso deve ser preenchida automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;j. Na página **Configurar Nomes Alternativos de Entidades Adicionais** página, você precisa adicionar os nomes alternativos de entidades adicionais que você precisa.
    
&nbsp;&nbsp;&nbsp;k. Na página **Resumo da solicitação** , verificar as informações do certificado que será usado para gerar a solicitação. Se for necessário fazer alterações, volte e as faça agora.
    
&nbsp;&nbsp;&nbsp;l. Clique em **próximo** para gerar o arquivo CSR, que você precisará fornecer para a autoridade de certificação (você pode também clicar em **Exibir Log** para examinar o log para a solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;m. Depois que a solicitação tiver sido gerada, é possível clicar em **Exibir** para examinar o certificado e em **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser determinado para a sua AC, para que um certificado seja gerado e você o importe para este computador na próxima seção.
    

### <a name="4-import-the-certificate"></a>4. importar o certificado

&nbsp;&nbsp;&nbsp;um. Faça logon, como membro do grupo Administradores local, para o servidor de borda que você fez sua solicitação de certificado a partir do último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No Assistente de implantação, ao lado de etapa 3 de **. Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Tarefas de Certificado Disponíveis**, clique em  **Importar um certificado de um arquivo .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Na página **Importar Certificado**, digite o caminho completo e o nome do arquivo do certificado você tem na seção anterior (ou é possível clicar em **Procurar** para localizar e escolher o arquivo dessa maneira).
    
&nbsp;&nbsp;&nbsp;f. Se você está importando certificados para outros membros do seu pool de borda e seu certificado contém uma chave privada, não deixe de marcar a caixa de seleção **que contém a chave privada do certificado do arquivo de certificado** e especifique a senha. Clique em **Avançar** para continuar.
    
&nbsp;&nbsp;&nbsp;f. Na página**Resumo** , clique em **Avançar** depois de confirmar as informações e **Concluir** depois que o certificado é importado com êxito.
    
 
### <a name="5-export-the-certificate"></a>5. exportar o certificado

&nbsp;&nbsp;&nbsp;um. Verifique se que você tiver feito logon no servidor de borda que você importou o certificado anteriormente, como membro do grupo Administradores local.
    
&nbsp;&nbsp;&nbsp;b. Clique em **Iniciar**, **Executar** (ou abrir **pesquisa** ), e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;c. No console do MMC, clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa **Adicionar ou Remover Snap-ins**, clique em **Certificados**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa de diálogo de snap-in de **Certificados**, escolha  **Conta do computador**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa de diálogo **Selecionar Computador**, selecione **computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK**, e a configuração do console MMC será concluída.
    
&nbsp;&nbsp;&nbsp;g. Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados. Clique duas vezes em **Pessoal**e em **Certificados**.
    
  > [!NOTE]
  > Você pode estar aqui e você não vir a todos os certificados no certificados pessoais armazenar para o computador local. Você não precisa de busca ao redor, se a chave não existe, do importado certificado não tinha uma chave privada associada a ela. Tente a solicitação e importar as etapas acima mais uma vez e, se você tiver certeza de que você obteve muito direita, fale com o administrador da autoridade de certificação ou provedor. 
  
&nbsp;&nbsp;&nbsp;h. No **repositório de certificados pessoais** do computador local, clique com botão direito no certificado que você está exportando. Selecione **Todas as Tarefas** no menu resultante e, em seguida, clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;Eu. No **Assistente de Exportação de Certificado**, clique em  **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;j. Na caixa de diálogo **Exportar Formatos de Arquivo**, selecione **Troca de Informações Pessoais - PKCS#12 (.PFX)**e selecione:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eu. Incluir todos os certificados no caminho de certificação, se possível.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportar todas as propriedades avançadas.
    
   > [!NOTE]
   > **NUNCA** selecione **Excluir a chave privada se a exportação for realizada com sucesso**. Ele vai média que você precisará reimportar o certificado e a chave privada volta ao servidor de borda.
  
&nbsp;&nbsp;&nbsp;k. Se quiser atribuir uma senha para proteger a chave privada, você pode digitar uma senha para a chave privada. Insira a senha novamente para confirmar e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;l. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo **.pfx**. O caminho ou precisa ser acessado por outros servidores de borda no pool ou será necessário mover o arquivo por meio de mídia externa (por exemplo, uma unidade USB). Clique em **Next** quando você fez sua escolha.
    
&nbsp;&nbsp;&nbsp;m. Analise o resumo na caixa de diálogo **Concluindo o Assistente para Exportação de Certificados** e, em seguida, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
 
### <a name="6-assign-the-certificate"></a>6. atribuir o certificado

&nbsp;&nbsp;&nbsp;um. Em cada servidor de borda, no Assistente de implantação, ao lado de etapa 3 de **. Solicitar, instalar ou atribuir certificados**, clique em **executar novamente**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Atribuir um certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Atribuição de Certificado**, selecione  **Interno à Borda** na lista.
    
&nbsp;&nbsp;&nbsp;d. Na página **Repositório de certificados** , selecione o certificado que você importou para a borda interna (a partir da seção anterior).
    
&nbsp;&nbsp;&nbsp;f. Na página **Resumo de Atribuição de Certificado**, examine as configurações e, em seguida, clique em **Avançar** para atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;f. Na página de conclusão do assistente, clique em  **Concluir**.
    
&nbsp;&nbsp;&nbsp;g. Depois de concluir esse procedimento, é realmente uma boa ideia para abrir o snap-in MMC de certificados em cada servidor de borda, expanda **certificados (computador Local)**, expanda **pessoal**, clique em **certificados**e confirme se a borda interna certificado está listado no painel de detalhes.
    
### <a name="external-edge-interface-certificates"></a>Certificados de Interface de Borda Externa

 
### <a name="1-create-the-certificate-request"></a>1. criar a solicitação de certificado

&nbsp;&nbsp;&nbsp;um. Faça logon em um dos seus servidores de borda, inicie o Assistente de implantação e em **etapa 3: solicitar, instalar ou atribuir certificados, clique em executar** (ou **Executar novamente**, se você já executou este assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Solicitação de Certificado**, certifique-se que **Certificado da Borda Externa** está selecionado e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;d. Na página  **Solicitações Atrasadas ou Imediatas**, clique em  **Preparar a solicitação agora, mas enviá-la depois**.
    
&nbsp;&nbsp;&nbsp;f. Na página **Arquivo de Solicitação de Certificado**, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert cer). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo padrão do Servidor da Web, marque a opção **Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada**.
    
&nbsp;&nbsp;&nbsp;g. Na página  Nome e Configurações de Segurança, siga estes procedimentos:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eu. Em **Nome amigável**, insira um nome de exibição para o certificado (como Borda Externa).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Em **Comprimento de bit**, escolha a comprimento de bit (o padrão é 2048, você pode aumentar e ter mais segurança, mas causará diminuição no desempenho).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Se você precisa de um certificado exportável, você deve marcar a caixa de seleção **Marcar chave privada de certificado como exportável**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;h. Na página **Informações da Organização**, insira o nome para sua organização e unidade organizacional (UO). É possível inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;Eu. Na página  **Informações Geográficas**, insira as informações de localização.
    
&nbsp;&nbsp;&nbsp;j. Na página **Nome da entidade/Nomes alternativos de entidades**, a informação necessária deve ser preenchida automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;k. Na página **Configuração de domínio SIP em nomes de entidade alternativos (SANs)** , marque a caixa de seleção do domínio para adicionar um sip.<sipdomain> entrada à lista de nomes alternativos da entidade.
    
&nbsp;&nbsp;&nbsp;l. Na página **Configurar Nomes Alternativos de Entidades Adicionais** página, você precisa adicionar os nomes alternativos de entidades adicionais que você precisa.
    
&nbsp;&nbsp;&nbsp;m. Na página **Resumo da solicitação** , verificar as informações do certificado que será usado para gerar a solicitação. Se for necessário fazer alterações, volte e as faça agora.
    
&nbsp;&nbsp;&nbsp;n. Quando você estiver pronto, clique em **próximo** para gerar o arquivo CSR, que você precisará fornecer para a autoridade de certificação (você pode também clicar em **Exibir Log** para examinar o log para a solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;o. Depois que a solicitação tiver sido gerada, é possível clicar em **Exibir** para examinar o certificado e em **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser determinado para a sua AC, para que um certificado seja gerado e você o importe para este computador na próxima seção.
    
&nbsp;&nbsp;&nbsp;p. (OPCIONAL) Você pode, ao apresentar o conteúdo do CSR, ser solicitado a apresentar certas informações, como segue (as CAs variam muito, portanto, isso pode não ser necessário):
    
  - **Microsoft** como plataforma de servidor
    
  - **IIS** como versão
    
  - **Servidor Web** como o tipo de uso
    
  - **PKCS7** como o formato de resposta
    
 
### <a name="2-import-the-certificate"></a>2. importar o certificado

&nbsp;&nbsp;&nbsp;um. Faça logon, como membro do grupo Administradores local, para o servidor de borda que você fez sua solicitação de certificado a partir do último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No Assistente de implantação, ao lado de etapa 3 de **. Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Tarefas de Certificado Disponíveis**, clique em  **Importar um certificado de um arquivo .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Na página **Importar Certificado**, digite o caminho completo e o nome do arquivo do certificado você tem na seção anterior (ou é possível clicar em **Procurar** para localizar e escolher o arquivo dessa maneira). Se o seu certificado contém uma chave privada, certifique-se de selecionar o **arquivo de certificado contém a chave privada do certificado**e insira a senha para a chave privada. Clique em **Avançar** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;f. Na página  **Importar Resumo de Certificado**, revise as informações do resumo e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na página **Executando comandos** , você pode revisar o resultado da importação quando ela for concluída, clicando em **Exibir Log**. Clique em **Concluir** para concluir a importação do certificado.
    
&nbsp;&nbsp;&nbsp;g. Se você tiver outros servidores de borda em um pool, você precisará siga os próximos dois procedimentos. Caso se trate de um servidor de borda autônomo, terminar com certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. exportar o certificado

&nbsp;&nbsp;&nbsp;um. Verifique se que você tiver feito logon no servidor de borda que você importou o certificado como um administrador local.
    
&nbsp;&nbsp;&nbsp;b. Clique em **Iniciar**, **Executar** (ou abrir **pesquisa** ), e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;c. No console do MMC, clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa **Adicionar ou Remover Snap-ins**, clique em **Certificados**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa de diálogo de snap-in de **Certificados**, escolha  **Conta do computador**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa de diálogo **Selecionar Computador**, selecione **computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK**, e a configuração do console MMC será concluída.
    
&nbsp;&nbsp;&nbsp;g. Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados. Clique duas vezes em **Pessoal**e em **Certificados**.
    
    > [!NOTE]
    > You may be here, and you don't see any certificates in the Certificates Personal store for the local computer. You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it. Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider. 
  
&nbsp;&nbsp;&nbsp;h. No **repositório de certificados pessoais** do computador local, clique com botão direito no certificado que você está exportando. Selecione **Todas as Tarefas** no menu resultante e, em seguida, clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;Eu. No **Assistente de Exportação de Certificado**, clique em  **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
    > [!NOTE]
    > If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it. You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.
  
&nbsp;&nbsp;&nbsp;j. Na caixa de diálogo Exportar Formatos de Arquivo, selecione Troca de Informações Pessoais - PKCS#12 (.PFX)  e selecione o seguinte:
    
 &nbsp;&nbsp;&nbsp;Eu. Incluir todos os certificados no caminho de certificação, se possível.
    
 &nbsp;&nbsp;&nbsp;II. Exportar todas as propriedades avançadas.
    
    > [!NOTE]
    > **NEVER** select **Delete the private key if the export is successful**. It'll mean you have to reimport the certificate and private key back to this Edge Server.
  
&nbsp;&nbsp;&nbsp;k. Se quiser atribuir uma senha para proteger a chave privada, você pode digitar uma senha para a chave privada. Insira a senha novamente para confirmar e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;l. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo **.pfx**. O caminho ou precisa ser acessado por outros servidores de borda no pool ou será necessário mover o arquivo por meio de mídia externa (por exemplo, uma unidade USB). Clique em **Next** quando você fez sua escolha.
    
&nbsp;&nbsp;&nbsp;m. Analise o resumo na caixa de diálogo **Concluindo o Assistente para Exportação de Certificados** e, em seguida, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
&nbsp;&nbsp;&nbsp;o. Agora, você precisará voltar para a importação a seção de certificado isso antes de importar o certificado para todos os servidores de borda restantes e prosseguir com a atribuição, veja a seguir.
    
 
### <a name="4-assign-the-certificate"></a>4. atribuir o certificado

&nbsp;&nbsp;&nbsp;um. No servidor de borda **EACH** , no Assistente de implantação, ao lado de etapa 3 de **. Solicitar, instalar ou atribuir certificados**, clique em **executar novamente**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Atribuir um certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Atribuição de certificado** , selecione **Borda externa** na lista.
    
&nbsp;&nbsp;&nbsp;d. Na página **Repositório de certificados** , selecione o certificado que você importou para a borda externa (a partir da seção anterior).
    
&nbsp;&nbsp;&nbsp;f. Na página **Resumo de Atribuição de Certificado**, examine as configurações e, em seguida, clique em **Avançar** para atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;f. Na página de conclusão do assistente, clique em  **Concluir**.
    
&nbsp;&nbsp;&nbsp;g. Depois de concluir esse procedimento, é realmente uma boa ideia para abrir o snap-in MMC de certificados em cada servidor, expanda **certificados (computador Local)**, expanda **pessoal**, clique em **certificados**e confirme se a borda interna certificado está listado no painel de detalhes.
    
   > [!NOTE]
    > Você também deverá configurar os certificados para seu servidor de proxy reverso. Que é abordado em servidores de Proxy reverso a instalação for Skype para tópico Business Server 2015. 
  
## <a name="starting-the-edge-servers"></a>Iniciando os servidores de borda

Depois que a instalação for concluída, você precisará iniciar os serviços em cada servidor de borda em sua implantação:
  
1. Em cada servidor de borda, no **Assistente para implantação**, próximo ao **etapa 4: iniciar serviços**, clique em **Executar**.
    
2. Na página **Iniciar Skype para serviços corporativos de servidor** , examine a lista de serviços e clique em **Avançar** para iniciar os serviços.
    
3. Depois dos serviços serem iniciados, clique em **Finalizar** para fechar o assistente.
    
4. (Opcional) Ainda na **Etapa 4: Iniciar Serviços**, clique em **Status de Serviços**.
    
5.  No **MMC de serviços** em cada servidor, verifique se que todos o Skype para serviços de Business Server 2015 estejam em execução.
    

