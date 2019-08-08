---
title: Implantar servidores de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Resumo: saiba como implantar servidores de borda em seu ambiente do Skype for Business Server.'
ms.openlocfilehash: 70355f6f00e8f38a13d74afd2d13c62a345fa063
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233881"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Implantar servidores de borda no Skype for Business Server
 
**Resumo:** Saiba como implantar servidores de borda em seu ambiente do Skype for Business Server.
  
As seções a seguir contêm etapas que devem ser seguidas após a análise do plano do Skype for Business Server para implantações do [servidor de borda na documentação do Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) . As etapas da implantação são:
  
- Interfaces de Rede
    
- Instalação
    
- Certificados
    
- Iniciando os servidores de borda
    
## <a name="network-interfaces"></a>Interfaces de Rede

Conforme observado no planejamento, você estará configurando a interface de rede com o DNS na rede de perímetro que hospeda seus servidores de borda ou sem DNS na rede de perímetro.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuração da interface com os servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Na sua interface externa, você configurará **um** dos seguintes:
    
   a. Três endereços IP estáticos na sub-rede da rede externa de perímetro e, em seguida, aponte o gateway padrão à interface interna do firewall externo. Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS de perímetro.
    
   b. Um endereço IP estático na sub-rede da rede externa de perímetro e, em seguida, aponte o gateway padrão à interface interna do firewall externo. Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS de perímetro. Essa configuração só será aceitável se você tiver configurado anteriormente sua topologia para ter valores não padrão nas atribuições de porta, que é abordado no artigo [criar sua topologia de borda para o Skype for Business Server](create-your-edge-topology.md) .
    
3. Na sua interface interna, configure um IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão. Defina as configurações do DNS do adaptador a fim de apontar para pelo menos um servidor DNS, preferencialmente um par de servidores DNS de perímetro.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, o Skype for Business Server e os servidores Exchange Unified Messaging (UM) residem.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuração da interface sem os servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Na sua interface externa, você configurará **um** dos seguintes:
    
   a. Três endereços IP estáticos na sub-rede da rede externa de perímetro. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definir o roteador de Internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS do adaptador a fim de apontar para um servidor de DNS externo, preferencialmente um par de servidores DNS externos.
    
   b. Um endereço IP estático na sub-rede da rede externa de perímetro. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definir o roteador de Internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS do adaptador a fim de apontar para um servidor DNS externo, ou preferencialmente para um par de servidores DNS externos. Essa configuração só será aceitável se você tiver configurado anteriormente sua topologia para ter valores não padrão nas atribuições de porta, que é abordado no artigo [criar sua topologia de borda para o Skype for Business Server](create-your-edge-topology.md) .
    
3. Na sua interface interna, configure um IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão. Deixe as configurações DNS do adaptador vazias.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, o Skype for Business Server e os servidores Exchange Unified Messaging (UM) residem.
    
5. Edite o arquivo de HOST em cada servidor de borda para conter um registro para o próximo servidor de salto ou IP virtual (VIP). Esse registro será o diretor, o servidor Standard Edition ou o pool Front-end que você configurou como o endereço do próximo salto do servidor de borda no construtor de topologias. Se você estiver usando o balanceamento de carga de DNS, inclua uma linha para cada membro do próximo pool de saltos.
    
## <a name="installation"></a>Instalação

Para concluir essas etapas com êxito, você precisará seguir as etapas no artigo [criar sua topologia de borda para o Skype for Business Server](create-your-edge-topology.md) .
  
1. Faça logon no servidor que você está configurando para a função de servidor de borda com uma conta que está no grupo de Administradores local.
    
2. Você precisará do arquivo de configuração de topologia que você copiou no final da documentação da topologia do servidor de borda neste computador. Acesse a mídia externa na qual você colocou o arquivo de configuração (como uma unidade USB ou compartilhamento).
    
3. Iniciar o **Assistente de implantação**.
    
4. Quando o assistente abrir, clique em **instalar ou atualizar o sistema do Skype for Business Server**.
    
5. O assistente executará verificações para ver se alguma coisa já está instalada. Como esta é a primeira vez que você executa o assistente, você desejará começar na **etapa 1. Instale o repositório de configuração local.**
    
6. A caixa de diálogo **Configurar réplica local do repositório de gerenciamento central** será exibida. Você precisará clicar em **importar de um arquivo (recomendado para servidores de borda)**.
    
7. A partir daqui, navegue para a localização da topologia que você exportou anteriormente, selecione o arquivo .zip, clique em **Abrir**e clique em **Avançar**.
    
8. O assistente de implantação lerá o arquivo de configuração e gravará o arquivo de configuração XML no computador local.
    
9. Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.
    
10. No assistente de implantação, clique em **etapa 2. Configurar ou remover componentes do Skype for Business Server**. Em seguida, o assistente instalará os componentes de borda do servidor do Skype for Business especificados no arquivo de configuração XML que foi armazenado no computador local.
    
11. Depois que a instalação for concluída, você poderá passar para as etapas na seção **certificados** abaixo.
    
## <a name="certificates"></a>Certificados

Os requisitos de certificado para o servidor de borda podem ser encontrados na documentação de planejamento do certificado de borda. As etapas para configurar os certificados estão indicadas abaixo.
  
> [!NOTE]
> Ao executar o assistente de certificado, você precisa estar conectado como uma conta com as permissões corretas para o tipo de modelo de certificado que você vai usar. Por padrão, uma solicitação de certificado do Skype for Business Server vai usar o modelo de certificado de servidor Web. Se você estiver conectado com uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado por meio desse modelo, verifique se as permissões de registro foram atribuídas ao grupo para usar esse modelo. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de Interface de Borda Interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. baixe ou exporte a cadeia de certificação da CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;um. Fazer o download usando o site da web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Configur. Conecte-se a um servidor do Skype for Business na sua rede interna como membro do grupo Administradores local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Abra o **início**e **Execute** (ou **pesquise** e **Execute** ) e, em seguida, digite o seguinte:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por exemplo:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Na página da Web do certsrv da CA de emissão, em **Selecione uma tarefa**, clique em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Em  **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**, clique em  **Fazer download de cadeia de certificados de autoridade de certificação**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;m. Na caixa de diálogo  **Download de Arquivo**, clique em  **Salvar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salve o arquivo. p7b na unidade de disco rígido no servidor e copie-o para uma pasta em cada um dos seus servidores de borda.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportar usando MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Configur. Você pode exportar o certificado raiz da AC de qualquer máquina associada ao domínio, usando o MMC. Ir para **Iniciar** e **Executar**, ou abrir **Pesquisa**, e digite **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. No console MMC (Console de Gerenciamento Microsoft), clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Na lista de diálogos **Adicionar ou Remover Snap-ins**, selecione **Certificados**, e depois clique em **Adicionar**. Ao ser solicitado, selecione **Conta do Computador**, e depois clicar em **Avançar**. Na caixa de diálogo **Selecionar Computador**, selecione **Computador Local**. Clique em **Concluir**, e depois em **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Expanda **Certificates (computador local)**. Expanda as **autoridades de certificação raiz confiáveis**. Selecione **certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;m. Clique no certificado raiz emitido por sua AC. Clique com o botão direito no certificado, escolha **Todas as Tarefas** no menu, e selecione **Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. O **Assistente de Exportação de Certificado** será aberto. Click **Next**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Na caixa de diálogo **Exportar o Formato do Arquivo**, escolha o formato que deseja exportar. Nossa recomendação é **Cryptographic Message Syntax Standard - PKCS #7 Certificados (P7b)**. Se isso também for sua opção, lembre-se de também marcar a caixa de seleção **incluir todos os certificados no caminho de certificação, se possível** , pois isso também exportará a cadeia de certificados, incluindo o certificado da CA raiz e qualquer certificado intermediário. Click **Next**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Na caixa de diálogo **Arquivo para exportar**, na entrada do nome do arquivo, digite um caminho e o nome de arquivo (a extensão padrão seria .p7b) para o certificado exportado. Se for mais fácil, escolha o botão **procurar** para ir para o local onde você deseja salvar o certificado exportado e nomeie o certificado exportado aqui. Clique em **salvar**e, em seguida, **próximo** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Revise o resumo de suas ações e clique em **Concluir** para concluir a exportação do certificado. Clique em **OK** para confirmar que a exportação foi bem sucedida.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ActiveX. Copie o arquivo. p7b para cada um dos seus servidores de borda.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importar a cadeia de certificação da CA

&nbsp;&nbsp;&nbsp;um. Em cada servidor de borda, abra o MMC (escolha **Iniciar** e **executar**, ou **Pesquisar**e digite **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;b. No menu **Arquivo**, clique em  **Adicionar/Remover Snap-in**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;partição. Na caixa de diálogo **Adicionar ou Remover Snap-ins**, clique em  **Certificados**e, em seguida, clique em  **Adicionar**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.
    
&nbsp;&nbsp;&nbsp;vocálico. Na caixa de diálogo **Selecionar computador**, certifique-se de que a opção **Computador local: (o computador em que este console está sendo executado)** esteja marcada e clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;letra. Clique em **Fechar**e, em seguida, clicar em **OK**.
    
&nbsp;&nbsp;&nbsp;p. Na árvore do console, expanda **Certificados (computador local)**, clique com o botão direito do mouse em **Autoridades de Certificação Raiz Confiáveis**, vá para  **Todas as tarefas**e clique em **Importar**.
    
&nbsp;&nbsp;&nbsp;u. No assistente exibido, na caixa de texto **Arquivo a ser importado**, especifique o nome do arquivo do certificado (o nome dado ao arquivo .p7b na seção anterior). Click **Next**.
    
&nbsp;&nbsp;&nbsp;Configur. Deixe o botão de opção em **Colocar todos os certificados no repositório a seguir, como Autoridades de Certificação Raiz Confiáveis** devem ser selecionados. Click **Next**.
    
&nbsp;&nbsp;&nbsp;j. Revise o resumo e clique em **Concluir** para terminar a importação.
    
&nbsp;&nbsp;&nbsp;k. Isso precisará ser feito para cada servidor de borda que você estiver implantando.
    
### <a name="3-create-the-certificate-request"></a>3. criar a solicitação de certificado

&nbsp;&nbsp;&nbsp;um. Faça logon em um dos seus servidores de borda, inicie o assistente de implantação e, na **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar** (ou **executar novamente**, se você já tiver executado este assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Solicitação de Certificado**, certifique-se que **Certificado da Borda Interna** está selecionado e clique em **Solicitação**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **solicitações atrasadas ou imediatas** , escolha **enviar a solicitação imediatamente para uma autoridade de certificação online** se você tiver acesso a uma pessoa do ambiente de borda ou **preparar a solicitação agora, mas enviá-la mais tarde** de outra forma.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página **Arquivo de Solicitação de Certificado**, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert cer). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;vocálico. Na página  **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo padrão do Servidor da Web, marque a caixa de seleção **Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada**. Caso contrário, não continue com os procedimentos.
    
&nbsp;&nbsp;&nbsp;letra. Na página  Nome e Configurações de Segurança, siga estes procedimentos:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Configur. Em **Nome amigável**, digite um nome de exibição para o certificado (por exemplo, Borda Interna).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Em **Comprimento de bit**, escolha a comprimento de bit (o padrão é 2048, você pode aumentar e ter mais segurança, mas causará diminuição no desempenho).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Se você precisa de um certificado exportável, você deve marcar a caixa de seleção **Marcar chave privada de certificado como exportável**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Click **Next**.
    
&nbsp;&nbsp;&nbsp;p. Na página **Informações da Organização**, insira o nome para sua organização e unidade organizacional (UO). É possível inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;u. Na página  **Informações Geográficas**, insira as informações de localização.
    
&nbsp;&nbsp;&nbsp;Configur. Na página **Nome de Entidade/Nomes alternativos de Entidades**, isso deve ser preenchida automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;j. Na página **Configurar Nomes Alternativos de Entidades Adicionais** página, você precisa adicionar os nomes alternativos de entidades adicionais que você precisa.
    
&nbsp;&nbsp;&nbsp;k. Na página de **Resumo de solicitação** , examine as informações de certificado que serão usadas para gerar sua solicitação. Se for necessário fazer alterações, volte e as faça agora.
    
&nbsp;&nbsp;&nbsp;t. Em seguida, clique em **Avançar** para gerar o arquivo CSR que você precisará fornecer à CA (você também pode clicar em **Exibir log** para ver o log para a solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;m. Depois que a solicitação tiver sido gerada, é possível clicar em **Exibir** para examinar o certificado e em **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser determinado para a sua AC, para que um certificado seja gerado e você o importe para este computador na próxima seção.
    

### <a name="4-import-the-certificate"></a>4. importar o certificado

&nbsp;&nbsp;&nbsp;um. Faça logon como membro do grupo Administradores local, no servidor de borda em que você fez a solicitação de certificado no último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No assistente de implantação, ao lado da **etapa 3. Solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **Tarefas de Certificado Disponíveis**, clique em  **Importar um certificado de um arquivo .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página **Importar Certificado**, digite o caminho completo e o nome do arquivo do certificado você tem na seção anterior (ou é possível clicar em **Procurar** para localizar e escolher o arquivo dessa maneira).
    
&nbsp;&nbsp;&nbsp;vocálico. Se você estiver importando certificados para outros membros do seu pool de bordas e seu certificado contiver uma chave privada, certifique-se de selecionar a caixa de seleção o **arquivo de certificado que contém a chave privada do certificado** e especifique a senha. Clique em **Avançar** para continuar.
    
&nbsp;&nbsp;&nbsp;letra. Na página**Resumo** , clique em **Avançar** depois de confirmar as informações e em **concluir** quando o certificado for importado com êxito.
    
 
### <a name="5-export-the-certificate"></a>5. exporte o certificado

&nbsp;&nbsp;&nbsp;um. Verifique se você fez logon no servidor de borda para o qual você importou o certificado anteriormente, como membro do grupo Administradores local.
    
&nbsp;&nbsp;&nbsp;b. Clique em **Iniciar**, **executar** (ou abrir **pesquisa** ) e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;partição. No console do MMC, clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na caixa **Adicionar ou Remover Snap-ins**, clique em **Certificados**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;vocálico. Na caixa de diálogo de snap-in de **Certificados**, escolha  **Conta do computador**. Click **Next**.
    
&nbsp;&nbsp;&nbsp;letra. Na caixa de diálogo **Selecionar Computador**, selecione **computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK**, e a configuração do console MMC será concluída.
    
&nbsp;&nbsp;&nbsp;p. Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados. Clique duas vezes em **Pessoal**e em **Certificados**.
    
  > [!NOTE]
  > Você pode estar aqui e não verá nenhum certificado no repositório pessoal de certificados do computador local. Você não precisa procurar, se a chave não estiver presente, o certificado importado não terá uma chave privada associada a ele. Experimente as etapas de solicitação e de importação acima de mais uma vez e, se você tiver certeza de que está tudo certo, fale com o administrador ou o provedor da autoridade de certificação. 
  
&nbsp;&nbsp;&nbsp;u. No **armazenamento de certificados pessoal** do computador local, clique com o botão direito do mouse no certificado que você está exportando. Selecione **Todas as Tarefas** no menu resultante e, em seguida, clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;Configur. No **Assistente de Exportação de Certificado**, clique em  **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;j. Na caixa de diálogo **Exportar Formatos de Arquivo**, selecione **Troca de Informações Pessoais - PKCS#12 (.PFX)** e selecione:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Configur. Incluir todos os certificados no caminho de certificação, se possível.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportar todas as propriedades avançadas.
    
   > [!NOTE]
   > **NUNCA** selecione **Excluir a chave privada se a exportação for realizada com sucesso**. Significa que você precisará importar novamente o certificado e a chave privada para este servidor de borda.
  
&nbsp;&nbsp;&nbsp;k. Se quiser atribuir uma senha para proteger a chave privada, você pode digitar uma senha para a chave privada. Insira a senha novamente para confirmar e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;t. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo **.pfx**. O caminho precisa estar acessível para os outros servidores de borda do pool, ou você precisará mover o arquivo por meio de mídia externa (como uma unidade USB). Clique em **Avançar** quando tiver feito a opção.
    
&nbsp;&nbsp;&nbsp;m. Analise o resumo na caixa de diálogo **Concluindo o Assistente para Exportação de Certificados** e, em seguida, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
 
### <a name="6-assign-the-certificate"></a>6. atribuir o certificado

&nbsp;&nbsp;&nbsp;um. Em cada servidor de borda, no assistente de implantação, ao lado da **etapa 3. Solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Atribuir um certificado existente**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **Atribuição de Certificado**, selecione  **Interno à Borda** na lista.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página **repositório de certificados** , selecione o certificado que você importou para a borda interna (da seção anterior).
    
&nbsp;&nbsp;&nbsp;vocálico. Na página **Resumo de Atribuição de Certificado**, examine as configurações e, em seguida, clique em **Avançar** para atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;letra. Na página de conclusão do assistente, clique em  **Concluir**.
    
&nbsp;&nbsp;&nbsp;p. Depois de concluir esse procedimento, é uma boa ideia abrir o snap-in do MMC de certificados em cada servidor de borda, expandir **certificados (computador local)**, expandir **pessoal**, clicar em **certificados**e confirmar que a borda interna o certificado está listado no painel detalhes.
    
### <a name="external-edge-interface-certificates"></a>Certificados de Interface de Borda Externa

 
### <a name="1-create-the-certificate-request"></a>1. criar a solicitação de certificado

&nbsp;&nbsp;&nbsp;um. Faça logon em um dos seus servidores de borda, inicie o assistente de implantação e, na **etapa 3: solicitar, instalar ou atribuir certificados, clique em executar** (ou **executar novamente**, se você já tiver executado este assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **Solicitação de Certificado**, certifique-se que **Certificado da Borda Externa** está selecionado e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página  **Solicitações Atrasadas ou Imediatas**, clique em  **Preparar a solicitação agora, mas enviá-la depois**.
    
&nbsp;&nbsp;&nbsp;vocálico. Na página **Arquivo de Solicitação de Certificado**, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert cer). Click **Next**.
    
&nbsp;&nbsp;&nbsp;letra. Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo padrão do Servidor da Web, marque a opção **Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada**.
    
&nbsp;&nbsp;&nbsp;p. Na página  Nome e Configurações de Segurança, siga estes procedimentos:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Configur. Em **Nome amigável**, insira um nome de exibição para o certificado (como Borda Externa).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Em **Comprimento de bit**, escolha a comprimento de bit (o padrão é 2048, você pode aumentar e ter mais segurança, mas causará diminuição no desempenho).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Se você precisa de um certificado exportável, você deve marcar a caixa de seleção **Marcar chave privada de certificado como exportável**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Click **Next**.
    
&nbsp;&nbsp;&nbsp;u. Na página **Informações da Organização**, insira o nome para sua organização e unidade organizacional (UO). É possível inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;Configur. Na página  **Informações Geográficas**, insira as informações de localização.
    
&nbsp;&nbsp;&nbsp;j. Na página **Nome da entidade/Nomes alternativos de entidades**, a informação necessária deve ser preenchida automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;k. Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , marque a caixa de seleção domínio para adicionar um SIP.<sipdomain> entrada para a lista nomes alternativos da entidade.
    
&nbsp;&nbsp;&nbsp;t. Na página **Configurar Nomes Alternativos de Entidades Adicionais** página, você precisa adicionar os nomes alternativos de entidades adicionais que você precisa.
    
&nbsp;&nbsp;&nbsp;m. Na página de **Resumo de solicitação** , examine as informações de certificado que serão usadas para gerar sua solicitação. Se for necessário fazer alterações, volte e as faça agora.
    
&nbsp;&nbsp;&nbsp;n. Quando estiver pronto, clique em **Avançar** para gerar o arquivo do CSR que você precisará fornecer à CA (você também pode clicar em **Exibir log** para ver o log para a solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;u. Depois que a solicitação tiver sido gerada, é possível clicar em **Exibir** para examinar o certificado e em **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser determinado para a sua AC, para que um certificado seja gerado e você o importe para este computador na próxima seção.
    
&nbsp;&nbsp;&nbsp;p. (OPCIONAL) Você pode, ao apresentar o conteúdo do CSR, ser solicitado a apresentar certas informações, como segue (as CAs variam muito, portanto, isso pode não ser necessário):
    
  - **Microsoft** como plataforma de servidor
    
  - **IIS** como versão
    
  - **Servidor Web** como o tipo de uso
    
  - **PKCS7** como o formato de resposta
    
 
### <a name="2-import-the-certificate"></a>2. importar o certificado

&nbsp;&nbsp;&nbsp;um. Faça logon como membro do grupo Administradores local, no servidor de borda em que você fez a solicitação de certificado no último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No assistente de implantação, ao lado da **etapa 3. Solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **Tarefas de Certificado Disponíveis**, clique em  **Importar um certificado de um arquivo .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página **Importar Certificado**, digite o caminho completo e o nome do arquivo do certificado você tem na seção anterior (ou é possível clicar em **Procurar** para localizar e escolher o arquivo dessa maneira). Se o certificado contiver uma chave privada, certifique-se de selecionar **arquivo de certificado contém a chave privada do certificado**e digite a senha da chave privada. Clique em **Avançar** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;vocálico. Na página  **Importar Resumo de Certificado**, revise as informações do resumo e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;letra. Na página **comandos em execução** , você pode revisar o resultado da importação quando ele é concluído clicando em **Exibir log**. Clique em **Concluir** para concluir a importação do certificado.
    
&nbsp;&nbsp;&nbsp;p. Se houver outros servidores de borda em um pool, você precisará seguir os dois próximos procedimentos também. Se for um servidor de borda autônomo, você será concluído com certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. exporte o certificado

&nbsp;&nbsp;&nbsp;um. Verifique se você fez logon no servidor de borda em que você importou o certificado como administrador local.
    
&nbsp;&nbsp;&nbsp;b. Clique em **Iniciar**, **executar** (ou abrir **pesquisa** ) e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;partição. No console do MMC, clique em **Arquivo**e, em seguida, clique em **Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na caixa **Adicionar ou Remover Snap-ins**, clique em **Certificados**e, em seguida, clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;vocálico. Na caixa de diálogo de snap-in de **Certificados**, escolha  **Conta do computador**. Click **Next**.
    
&nbsp;&nbsp;&nbsp;letra. Na caixa de diálogo **Selecionar Computador**, selecione **computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK**, e a configuração do console MMC será concluída.
    
&nbsp;&nbsp;&nbsp;p. Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados. Clique duas vezes em **Pessoal**e em **Certificados**.
    
   > [!NOTE]
   > Você pode estar aqui e não verá nenhum certificado no repositório pessoal de certificados do computador local. Você não precisa procurar, se a chave não estiver presente, o certificado importado não terá uma chave privada associada a ele. Experimente as etapas de solicitação e de importação acima de mais uma vez e, se você tiver certeza de que está tudo certo, fale com o administrador ou o provedor da autoridade de certificação. 
  
&nbsp;&nbsp;&nbsp;u. No **armazenamento de certificados pessoal** do computador local, clique com o botão direito do mouse no certificado que você está exportando. Selecione **Todas as Tarefas** no menu resultante e, em seguida, clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;Configur. No **Assistente de Exportação de Certificado**, clique em  **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
   > [!NOTE]
   > Se **Sim, exportar a chave privada** não está disponível, a chave privada deste certificado não foi marcada para exportação antes de você. Você precisa solicitar o certificado do provedor novamente, com a chave privada definida como exportação, antes de realizar a operação com sucesso.
  
&nbsp;&nbsp;&nbsp;j. Na caixa de diálogo Exportar Formatos de Arquivo, selecione Troca de Informações Pessoais - PKCS#12 (.PFX)  e selecione o seguinte:
    
 &nbsp;&nbsp;&nbsp;Configur. Incluir todos os certificados no caminho de certificação, se possível.
    
 &nbsp;&nbsp;&nbsp;II. Exportar todas as propriedades avançadas.
    
   > [!NOTE]
   > **NUNCA** selecione **Excluir a chave privada se a exportação for realizada com sucesso**. Significa que você precisará importar novamente o certificado e a chave privada para este servidor de borda.
  
&nbsp;&nbsp;&nbsp;k. Se quiser atribuir uma senha para proteger a chave privada, você pode digitar uma senha para a chave privada. Insira a senha novamente para confirmar e clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;t. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo **.pfx**. O caminho precisa estar acessível para os outros servidores de borda do pool, ou você precisará mover o arquivo por meio de mídia externa (como uma unidade USB). Clique em **Avançar** quando tiver feito a opção.
    
&nbsp;&nbsp;&nbsp;m. Analise o resumo na caixa de diálogo **Concluindo o Assistente para Exportação de Certificados** e, em seguida, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
&nbsp;&nbsp;&nbsp;u. Agora, você precisará voltar para a seção importar o certificado antes dele e importar o certificado para todos os seus servidores de borda restantes e continuar com a atribuição, abaixo.
    
 
### <a name="4-assign-the-certificate"></a>4. atribuir o certificado

&nbsp;&nbsp;&nbsp;um. Em **cada** servidor de borda, no assistente de implantação, ao lado da **etapa 3. Solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em  **Atribuir um certificado existente**.
    
&nbsp;&nbsp;&nbsp;partição. Na página **atribuição de certificado** , selecione **borda externa** na lista.
    
&nbsp;&nbsp;&nbsp;desenvolvimento. Na página **repositório de certificados** , selecione o certificado que você importou para a borda externa (da seção anterior).
    
&nbsp;&nbsp;&nbsp;vocálico. Na página **Resumo de Atribuição de Certificado**, examine as configurações e, em seguida, clique em **Avançar** para atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;letra. Na página de conclusão do assistente, clique em  **Concluir**.
    
&nbsp;&nbsp;&nbsp;p. Depois de concluir esse procedimento, é uma boa ideia abrir o snap-in do MMC de certificados em cada servidor, expandir **certificados (computador local)**, expandir **pessoal**, clicar em **certificados**e confirmar que a borda interna o certificado está listado no painel detalhes.
    
   > [!NOTE]
   > Você também deverá configurar os certificados para seu servidor de proxy reverso. 
  
## <a name="starting-the-edge-servers"></a>Iniciando os servidores de borda

Depois que a instalação for concluída, você precisará iniciar os serviços em cada servidor de borda na sua implantação:
  
1. Em cada servidor de borda, no **Assistente de implantação**, ao lado de **etapa 4: Iniciar serviços**, clique em **executar**.
    
2. Na página **iniciar o Skype for Business Server Services** , examine a lista de serviços e clique em **Avançar** para iniciar os serviços.
    
3. Depois dos serviços serem iniciados, clique em **Finalizar** para fechar o assistente.
    
4. (Opcional) Ainda na **Etapa 4: Iniciar Serviços**, clique em **Status de Serviços**.
    
5.  No **MMC serviços** em cada servidor, verifique se todos os serviços do Skype for Business Server estão em execução.
    

