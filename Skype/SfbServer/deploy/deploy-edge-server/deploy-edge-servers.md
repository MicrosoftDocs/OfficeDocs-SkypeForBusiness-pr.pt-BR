---
title: Implantar servidores de borda Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Resumo: Saiba como implantar servidores de borda em seu ambiente Skype for Business Server ambiente.'
ms.openlocfilehash: 30beb7b42b2f77e82d83768d918102cbaa0f7f5e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852725"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Implantar servidores de borda Skype for Business Server
 
**Resumo:** Saiba como implantar Servidores de Borda em seu Skype for Business Server ambiente.
  
As seções a seguir contêm etapas que devem ser seguidas após Skype for Business Server plano para implantações do [Servidor](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) de Borda na Skype for Business Server documentação foi revisada. As etapas de implantação são as seguintes:
  
- Interfaces de Rede
    
- Instalação
    
- Certificados
    
- Iniciando os Servidores de Borda
    
## <a name="network-interfaces"></a>Interfaces de Rede

Como é possível ver em Planejamento, você estará configurando sua interface de rede com DNS na rede de perímetro que hospeda seus Servidores de Borda ou sem DNS na rede de perímetro.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuração de interface com servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Em sua interface externa, você configurará **um** dos seguintes:
    
   a. Três endereços IP estáticos na sub-rede de rede de perímetro externo e apontam o gateway padrão para a interface interna do firewall externo. Configure as configurações dns do adaptador para apontar para um par de servidores DNS de perímetro.
    
   b. Um endereço IP estático na sub-rede de rede de perímetro externo e aponte o gateway padrão para a interface interna do firewall externo. Configure as configurações dns do adaptador para apontar para um par de servidores DNS de perímetro. Essa configuração só será aceitável se você tiver configurado anteriormente sua topologia para ter valores não padrão nas atribuições de porta, o que é abordado no artigo Criar sua [topologia](create-your-edge-topology.md) de Borda para Skype for Business Server.
    
3. Em sua interface interna, configure um IP estático na sub-rede de rede de perímetro interno e não de definir um gateway padrão. Configure as configurações dns do adaptador para apontar para pelo menos um servidor DNS, mas preferencialmente um par de servidores DNS de perímetro.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, Skype for Business Server e Exchange de Unificação de Mensagens (UM) residem.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuração de interface sem servidores DNS na rede de perímetro

1. Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.
    
    > [!NOTE]
    > As sub-redes interna e externa não devem ser roteáveis ente si. 
  
2. Em sua interface externa, você configurará **um** dos seguintes:
    
   a. Três endereços IP estáticos na sub-rede de rede de perímetro externo. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definindo o roteador voltado para a Internet ou o firewall externo como o gateway padrão. Configure as configurações dns do adaptador para apontar para um servidor DNS externo, idealmente um par de servidores DNS externos.
    
   b. Um endereço IP estático na sub-rede de rede de perímetro externo. Você também precisará configurar o gateway padrão na interface externa, por exemplo, definindo o roteador voltado para a Internet ou o firewall externo como o gateway padrão. Configure as configurações dns do adaptador para apontar para um servidor DNS externo ou, idealmente, um par de servidores DNS externos. Essa configuração só será aceitável se você tiver configurado anteriormente sua topologia para ter valores não padrão nas atribuições de porta, o que é abordado no artigo Criar sua [topologia](create-your-edge-topology.md) de Borda para Skype for Business Server.
    
3. Em sua interface interna, configure um IP estático na sub-rede de rede de perímetro interno e não de definir um gateway padrão. Também deixe as configurações DNS do adaptador vazias.
    
4. Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, Skype for Business Server e Exchange de Unificação de Mensagens (UM) residem.
    
5. Edite o arquivo HOST em cada Servidor de Borda para conter um registro para o servidor de próximo salto ou IP virtual (VIP). Esse registro será o Diretor, Edição Standard servidor ou pool de Front-End configurado como o endereço de próximo salto do Servidor de Borda no Construtor de Topologias. Se você estiver usando o balanceamento de carga DNS, inclua uma linha para cada membro do pool de próximo salto.
    
## <a name="installation"></a>Instalação

Para concluir essas etapas com êxito, você precisará ter seguido as etapas no artigo Criar sua [topologia](create-your-edge-topology.md) de borda para Skype for Business Server.
  
1. Faça logoff no servidor que você está configurando para a função servidor de borda com uma conta que está no grupo do Administrador local.
    
2. Você precisará do arquivo de configuração de topologia que copiou no final da documentação de Topologia do Servidor de Borda neste computador. Acesse a mídia externa em que você colocou esse arquivo de configuração (como uma unidade USB ou compartilhamento).
    
3. Inicie o **Assistente de Implantação**.
    
4. Depois que o assistente for aberto, clique **em Instalar ou Atualizar Skype for Business Server Sistema.**
    
5. O assistente executará verificações para ver se alguma coisa já está instalada. Como esta é a primeira vez que o assistente é executado, você vai querer começar na **Etapa 1. Instalar o Armazenamento de Configuração Local.**
    
6. A **caixa de diálogo Configurar Réplica Local do Armazenamento de Gerenciamento Central** será exibida. Você precisa clicar em **Importar de um arquivo (Recomendado para Servidores de Borda)**.
    
7. A partir daqui, navegue até o local da topologia que você exportou anteriormente, selecione o arquivo .zip, clique em **Abrir** e clique em **Próximo**.
    
8. O Assistente de Implantação lerá o arquivo de configuração e gravará o arquivo de configuração XML no computador local.
    
9. Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.
    
10. No Assistente de Implantação, clique **em Etapa 2. Instalação ou remover Skype for Business Server componentes**. Em seguida, o assistente instalará os Skype for Business Server de Borda especificados no arquivo de configuração XML armazenado no computador local.
    
11. Depois que a instalação é concluída, você pode mover para as etapas na seção **Certificados** abaixo.
    
## <a name="certificates"></a>Certificados

Os requisitos de certificado para o Servidor de Borda podem ser encontrados na documentação planejamento de certificados de borda. As etapas para configurar certificados estão abaixo.
  
> [!NOTE]
> Ao executar o Assistente de Certificado, você precisa estar conectado como uma conta com as permissões corretas para o tipo de modelo de certificado que você vai usar. Por padrão, Skype for Business Server solicitação de certificado de usuário usará o modelo de certificado do Servidor Web. Se você estiver conectado a uma conta membro do grupo RTCUniversalServerAdmins para solicitar um certificado por meio deste modelo, verifique se o grupo recebeu as permissões Registrar para usar esse modelo. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de interface de Borda Interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Baixar ou exportar a cadeia de certificação ca

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. Baixar usando o site do certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Faça logoff Skype for Business Server em sua rede interna como membro do grupo local Administradores.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Abra **Iniciar** e **Executar** (ou **Pesquisar** **e** Executar ) e digite o seguinte:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por exemplo:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Na página web certificados da CA de emissão, em **Selecionar** uma tarefa, clique em Baixar um certificado ca, cadeia de certificados **ou CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Em **Baixar um certificado de AC, cadeia de certificados ou CRL,** clique em Baixar cadeia de **certificados de AC.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Na caixa **Baixar Arquivo,** clique em **Salvar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salve o arquivo .p7b na unidade de disco rígido no servidor e copie-o para uma pasta em cada um dos seus Servidores de Borda.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportar usando o MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Você pode exportar o certificado raiz da AC de qualquer máquina ingressada em domínio usando o MMC. Vá para **Iniciar** e **Executar** ou abra **Pesquisa** e digite **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. No console do MMC, clique em **Arquivo** e clique **em Adicionar/Remover Snap-In**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Na lista **de diálogo Adicionar ou Remover Snap-ins,** escolha **Certificados** e clique em **Adicionar**. Quando solicitado, selecione **Conta de Computador** e, em seguida, **Next**. No diálogo **Selecionar computador**, selecione **Computador local**. Clique **em Concluir** e, em **seguida, OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Expanda **Certificados (computador local)**. Expanda **Autoridades de Certificação Raiz Confiáveis**. Selecione **Certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Clique no certificado raiz emitido por sua AC. Clique com o botão direito do mouse no certificado, escolha **Todas as** Tarefas no menu e selecione **Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. O **Assistente de Exportação de Certificados** é aberto. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. Na caixa **de diálogo Exportar Formato de** Arquivo, escolha o formato para o qual você deseja exportar. Nossa recomendação é **Cryptographic Message Sintaxe Standard - PKCS #7 Certificates (P7b)**. Se essa também for sua escolha, lembre-se de também selecionar a caixa de seleção Incluir todos os certificados no caminho de certificação, se possível, pois isso também exportará a cadeia de certificados, incluindo o certificado ca raiz e quaisquer **certificados** Intermediários. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii. Na caixa de diálogo Arquivo para **Exportar,** na entrada nome do arquivo, digite um caminho e um nome de arquivo (a extensão padrão seria .p7b) para o certificado exportado. Se for mais fácil para você, escolha o botão **Procurar** para ir até o local para o qual você deseja salvar o certificado exportado e nomee o certificado exportado aqui. Clique **em** Salvar e **em Próximo** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Revise o resumo de suas ações e clique em **Concluir** para concluir a exportação do certificado. Clique em **OK** para confirmar que a exportação foi bem sucedida.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copie o arquivo .p7b para cada um de seus Servidores de Borda.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importar a cadeia de certificação ca

&nbsp;&nbsp;&nbsp;a. Em cada Servidor de Borda, abra o MMC (escolha **Iniciar** **e** Executar ou **Pesquisar** e digite **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;b. No menu **Arquivo,** clique **em Adicionar/Remover Snap-in** e escolha **Adicionar**.
    
&nbsp;&nbsp;&nbsp;c. Na caixa **Adicionar ou Remover Snap-ins,** clique em **Certificados** e clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa de diálogo **Snap-in de certificados**, clique em **Conta de computador** e em **Avançar**.
    
&nbsp;&nbsp;&nbsp;e. Na caixa **de diálogo Selecionar** Computador, verifique se a caixa de seleção Computador **Local: (o** computador em que o console está sendo executado) está selecionada e clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;f. Clique **em Fechar** e, em **seguida, OK**.
    
&nbsp;&nbsp;&nbsp;g. Na árvore de console, expanda **Certificados (Computador Local),** clique com o botão direito do mouse em Autoridades de Certificação Raiz **Confiáveis,** vá para Todas as Tarefas **e** clique em **Importar**.
    
&nbsp;&nbsp;&nbsp;h. No assistente que aparece,  na caixa de texto Arquivo a importar, especifique o nome de arquivo do certificado (o nome que você deu ao arquivo .p7b na seção anterior). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;i. Deixe o botão de opção em **Colocar todos os certificados no seguinte armazenamento, pois autoridades de** certificação raiz confiáveis devem ser selecionadas. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;j. Revise o resumo e clique em **Concluir** para concluir a importação.
    
&nbsp;&nbsp;&nbsp;k. Isso precisará ser feito para cada Servidor de Borda que você estiver implantando.
    
### <a name="3-create-the-certificate-request"></a>3. Crie a solicitação de certificado

&nbsp;&nbsp;&nbsp;a. Faça logoff em um de seus Servidores de Borda, inicie o Assistente de Implantação e, na Etapa **3: Solicitar,** Instalar ou Atribuir Certificados, clique em Executar **(ou** Executar **Novamente**, se você já tiver executado esse assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Solicitação de** Certificado, verifique se **o Certificado de Borda** Interna está selecionado e clique em **Solicitar**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Solicitações** Atrasadas ou Imediatas, escolha Enviar a solicitação imediatamente para uma autoridade de certificação **online** se você tiver acesso a uma de seu ambiente de Borda ou Preparar a solicitação **agora,** mas enviá-la posteriormente caso contrário.
    
&nbsp;&nbsp;&nbsp;d. Na página Arquivo de **Solicitação** de Certificado, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert.cer). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;e. Na página **Especificar Modelo** de Certificado Alternativo, para usar um modelo  diferente do modelo WebServer padrão, marque a caixa de seleção Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada. Caso contrário, não faça nada.
    
&nbsp;&nbsp;&nbsp;f. Na página Nome e Configurações de Segurança, faça o seguinte:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Em **Nome Amigável,** insira um nome de exibição para o certificado (como Borda Interna).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. Em **Comprimento de bit**, escolha seu comprimento de bit (o padrão é 2048, você pode ir mais alto e ser mais seguro, mas isso fará com que o desempenho seja lento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Se você precisar de um certificado exportável, verifique a caixa de seleção Marcar chave privada do certificado **como exportável.**
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;g. Na página **Informações da Organização,** insira o nome da sua organização e unidade organizacional (OU). Você pode inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;h. Na página **Informações Geográficas,** insira suas informações de local.
    
&nbsp;&nbsp;&nbsp;i. Na página **Nome da Pessoa/Nomes Alternativos** de Assunto, isso deve ser preenchido automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;j. Na página **Configurar Nomes Alternativos** de Assunto Adicionais, você precisa adicionar quaisquer nomes alternativos de assunto adicionais necessários.
    
&nbsp;&nbsp;&nbsp;k. Na página **Resumo de** Solicitação, procure as informações do certificado que serão usadas para gerar sua solicitação. Se precisar fazer alterações, volte e faça isso agora.
    
&nbsp;&nbsp;&nbsp;l. Em **seguida,** clique em Próximo para gerar o arquivo CSR que você precisará fornecer à CA (você também pode clicar em Exibir **Log** para ver o log da solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;m. Depois que a solicitação tiver sido gerada, você poderá clicar em **Exibir** para ver o certificado e **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser dado à sua AC, para que eles possam gerar um certificado para você importar para este computador na próxima seção.
    

### <a name="4-import-the-certificate"></a>4. Importar o certificado

&nbsp;&nbsp;&nbsp;a. Faça logoff, como membro do grupo de Administradores locais, no Servidor de Borda de onde você fez a solicitação de certificado no último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No Assistente de Implantação, ao lado da **Etapa 3. Solicitar, Instalar ou Atribuir Certificados,** clique **em Executar Novamente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Tarefas de Certificados Disponíveis,** clique em **Importar um certificado de um . Arquivo P7b, .pfx ou .cer.**
    
&nbsp;&nbsp;&nbsp;d. Na página **Importar Certificado,** digite o caminho completo e o nome do arquivo  do certificado que você recebeu na seção anterior (ou você pode clicar em Procurar para encontrar e escolher o arquivo dessa maneira).
    
&nbsp;&nbsp;&nbsp;e. Se você estiver importando certificados para outros membros do pool de Borda e seu certificado contiver uma chave privada, selecione a caixa de seleção **Arquivo** de certificado que contém a chave privada do certificado e especifique a senha. Clique em **Avançar** para continuar.
    
&nbsp;&nbsp;&nbsp;f. Na página **Resumo,** clique em **Próximo** depois de confirmar as informações e **Concluir quando** o certificado for importado com êxito.
    
 
### <a name="5-export-the-certificate"></a>5. Exportar o certificado

&nbsp;&nbsp;&nbsp;a. Certifique-se de ter conectado ao Servidor de Borda para o que você importou o certificado anteriormente, como membro do grupo administradores locais.
    
&nbsp;&nbsp;&nbsp;b. Clique **em Iniciar,** **Executar** (ou abrir **Pesquisa** ) e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;c. No console do MMC, clique em **Arquivo** e clique **em Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa **Adicionar ou Remover Snap-ins,** clique em **Certificados** e clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;e. Na caixa de diálogo Snap-in **Certificados,** escolha **Conta de computador**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa **de diálogo Selecionar Computador,** selecione **Computador local: (o** computador em que o console está sendo executado) . Clique em **Concluir**. Clique **em OK** e a configuração do console MMC é concluída.
    
&nbsp;&nbsp;&nbsp;g. Dê um duplo clique em **Certificados (Computador Local)** para expandir o repositório de certificados. Clique duas vezes **em Pessoal** e em **Certificados.**
    
  > [!NOTE]
  > Você pode estar aqui e não vê nenhum certificado no armazenamento Pessoal de Certificados para o computador local. Você não precisa procurar por aí, se a chave não estiver lá, o certificado importado não tinha uma chave privada associada a ela. Experimente a solicitação e importe as etapas acima mais uma vez e, se você tiver certeza de que tem todo esse direito, fale com seu administrador de AC ou provedor. 
  
&nbsp;&nbsp;&nbsp;h. No Armazenamento **Pessoal de Certificados** do computador local, clique com o botão direito do mouse no certificado que você está exportando. Selecione **Todas as Tarefas** no menu resultante e clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;i. No **Assistente para Exportação de Certificados**, clique em **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;j. Na caixa **de diálogo Exportar Formatos de** Arquivo, selecione Informações Pessoais Exchange - **PKCS#12 (. PFX)** e selecione o seguinte:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Inclua todos os certificados no caminho de certificação, se possível.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. Exportar todas as propriedades estendidas.
    
   > [!NOTE]
   > **NUNCA** selecione **Excluir a chave privada se a exportação for bem-sucedida**. Isso significa que você terá que reaportar o certificado e a chave privada de volta para este Servidor de Borda.
  
&nbsp;&nbsp;&nbsp;k. Se você quiser atribuir uma senha para proteger a chave privada, digite uma senha para a chave privada. Reentra na senha para confirmar e clique em **Próximo**.
    
&nbsp;&nbsp;&nbsp;l. Digite um caminho e um nome de arquivo para o certificado exportado, usando uma extensão de arquivo **de .pfx**. O caminho precisa estar acessível pelos outros Servidores de Borda no pool ou você precisará mover o arquivo por meio de mídia externa (como uma unidade USB). Clique **em Próximo** quando você fez sua escolha.
    
&nbsp;&nbsp;&nbsp;m. Revise o resumo na caixa **de diálogo Concluindo o Assistente** de Exportação de Certificados e clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
 
### <a name="6-assign-the-certificate"></a>6. Atribua o certificado

&nbsp;&nbsp;&nbsp;a. Em CADA Servidor de Borda, no Assistente de Implantação, ao lado da **Etapa 3. Solicitar, Instalar ou Atribuir Certificados,** clique **em Executar novamente**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificados Disponíveis,** clique em **Atribuir um certificado existente.**
    
&nbsp;&nbsp;&nbsp;c. Na página **Atribuição de Certificado**, selecione **Interno à Borda** na lista.
    
&nbsp;&nbsp;&nbsp;d. Na página **Armazenamento de** Certificados, selecione o certificado importado para a Borda interna (da seção anterior).
    
&nbsp;&nbsp;&nbsp;e. Na página **Resumo de Atribuição de** Certificado, procure as configurações e clique em Próximo **para** atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;f. Na página de conclusão do assistente, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;g. Depois de concluir esse procedimento, é uma ótima ideia abrir o snap-in MMC de certificados em cada Servidor de Borda, expandir **Certificados (computador local),** expandir **Pessoal,** clicar em **Certificados** e confirmar se o certificado de Borda interno está listado no painel de detalhes.
    
### <a name="external-edge-interface-certificates"></a>Certificados de interface de Borda Externa

 
### <a name="1-create-the-certificate-request"></a>1. Crie a solicitação de certificado

&nbsp;&nbsp;&nbsp;a. Faça logoff em um de seus Servidores de Borda, inicie o Assistente de Implantação e, na Etapa **3: Solicitar,** Instalar ou Atribuir Certificados, clique em Executar (ou Executar **novamente**, se você já tiver executado esse assistente).
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Solicitação de** Certificado, verifique se **o Certificado de Borda** Externa está selecionado e clique em **Próximo**.
    
&nbsp;&nbsp;&nbsp;d. Na página **Solicitações Atrasadas ou Imediatas**, clique em **Preparar a solicitação agora, mas enviá-la depois**.
    
&nbsp;&nbsp;&nbsp;e. Na página Arquivo de **Solicitação** de Certificado, insira a parte completa e o nome do arquivo para onde o arquivo será salvo (como c:\SkypeInternalEdgeCert.cer). Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na página **Especificar Modelo** de Certificado Alternativo, para usar um modelo  diferente do modelo WebServer padrão, marque a caixa de seleção Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada.
    
&nbsp;&nbsp;&nbsp;g. Na página Nome e Configurações de Segurança, faça o seguinte:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Em **Nome amigável,** insira um nome de exibição para o certificado (como Borda Externa).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. Em **Comprimento de bit**, escolha seu comprimento de bit (o padrão é 2048, você pode ir mais alto e ser mais seguro, mas isso fará com que o desempenho seja lento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Se você precisar de um certificado exportável, verifique a caixa de seleção Marcar chave privada do certificado **como exportável.**
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;h. Na página **Informações da Organização,** insira o nome da sua organização e unidade organizacional (OU). Você pode inserir sua divisão ou departamento (TI, por exemplo).
    
&nbsp;&nbsp;&nbsp;i. Na página **Informações Geográficas,** insira suas informações de local.
    
&nbsp;&nbsp;&nbsp;j. Na página **Nome do Assunto/Nomes Alternativos** de Assunto, as informações necessárias devem ser preenchidas automaticamente pelo assistente.
    
&nbsp;&nbsp;&nbsp;k. Na página Configuração de Domínio SIP em Nomes Alternativos de Assunto **(SANs),** marque a caixa de seleção domínio para adicionar um sip.\<sipdomain> entrada para a lista de nomes alternativos de assunto.
    
&nbsp;&nbsp;&nbsp;l. Na página **Configurar Nomes Alternativos** de Assunto Adicionais, você precisa adicionar quaisquer nomes alternativos de assunto adicionais necessários.
    
&nbsp;&nbsp;&nbsp;m. Na página **Resumo de** Solicitação, procure as informações do certificado que serão usadas para gerar sua solicitação. Se precisar fazer alterações, volte e faça isso agora.
    
&nbsp;&nbsp;&nbsp;n. Quando estiver pronto, clique em **Próximo** para gerar o arquivo CSR que você precisará fornecer à CA (você também pode clicar em Exibir **Log** para ver o log da solicitação de certificado).
    
&nbsp;&nbsp;&nbsp;o. Depois que a solicitação tiver sido gerada, você poderá clicar em **Exibir** para ver o certificado e **Concluir** para fechar a janela. O conteúdo do arquivo CSR precisa ser dado à sua AC, para que eles possam gerar um certificado para você importar para este computador na próxima seção.
    
&nbsp;&nbsp;&nbsp;p. (OPCIONAL) Você pode, ao enviar o conteúdo da CSR, ser solicitado a obter determinadas informações, da seguinte forma (as CAs variam muito, portanto, isso pode não ser necessário):
    
  - **Microsoft** como plataforma de servidor
    
  - **IIS** como a versão
    
  - **Servidor Web** como o tipo de uso
    
  - **PKCS7** como o formato de resposta
    
 
### <a name="2-import-the-certificate"></a>2. Importar o certificado

&nbsp;&nbsp;&nbsp;a. Faça logoff, como membro do grupo de Administradores locais, no Servidor de Borda de onde você fez a solicitação de certificado no último procedimento.
    
&nbsp;&nbsp;&nbsp;b. No Assistente de Implantação, ao lado da **Etapa 3. Solicitar, Instalar ou Atribuir Certificados,** clique **em Executar Novamente**.
    
&nbsp;&nbsp;&nbsp;c. Na página **Tarefas de Certificados Disponíveis,** clique em **Importar um certificado de um . Arquivo P7b, .pfx ou .cer.**
    
&nbsp;&nbsp;&nbsp;d. Na página **Importar Certificado,** digite o caminho completo e o nome do arquivo  do certificado que você recebeu na seção anterior (ou você pode clicar em Procurar para encontrar e escolher o arquivo dessa maneira). Se o certificado contiver uma chave privada, certifique-se de selecionar **Arquivo** de certificado contém a chave privada do certificado e insira a senha da chave privada. Clique **em Próximo** quando estiver pronto.
    
&nbsp;&nbsp;&nbsp;e. Na página **Importar Resumo de Certificados,** revise as informações de resumo e clique em **Próximo**.
    
&nbsp;&nbsp;&nbsp;f. Na página **Executando Comandos,** você pode revisar o resultado da importação quando estiver concluída clicando em **Exibir Log**. Clique **em Concluir** para concluir a importação do certificado.
    
&nbsp;&nbsp;&nbsp;g. Se você tiver outros Servidores de Borda em um pool, também precisará seguir os próximos dois procedimentos. Se for um Servidor de Borda autônomo, você terminará com certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. Exportar o certificado

&nbsp;&nbsp;&nbsp;a. Certifique-se de ter conectado ao Servidor de Borda para o que você importou o certificado como administrador local.
    
&nbsp;&nbsp;&nbsp;b. Clique **em Iniciar,** **Executar** (ou abrir **Pesquisa** ) e digite **MMC**.
    
&nbsp;&nbsp;&nbsp;c. No console do MMC, clique em **Arquivo** e clique **em Adicionar/Remover Snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Na caixa **Adicionar ou Remover Snap-ins,** clique em **Certificados** e clique em **Adicionar**.
    
&nbsp;&nbsp;&nbsp;e. Na caixa de diálogo Snap-in **Certificados,** escolha **Conta de computador**. Clique em **Avançar**.
    
&nbsp;&nbsp;&nbsp;f. Na caixa **de diálogo Selecionar Computador,** selecione **Computador local: (o** computador em que o console está sendo executado) . Clique em **Concluir**. Clique **em OK** e a configuração do console MMC é concluída.
    
&nbsp;&nbsp;&nbsp;g. Dê um duplo clique em **Certificados (Computador Local)** para expandir o repositório de certificados. **Clique duas vezes em Pessoal** e em **Certificados.**
    
   > [!NOTE]
   > Você pode estar aqui e não vê nenhum certificado no armazenamento Pessoal de Certificados para o computador local. Você não precisa procurar por aí, se a chave não estiver lá, o certificado importado não tinha uma chave privada associada a ela. Experimente a solicitação e importe as etapas acima mais uma vez e, se você tiver certeza de que tem todo esse direito, fale com seu administrador de AC ou provedor. 
  
&nbsp;&nbsp;&nbsp;h. No Armazenamento **Pessoal de Certificados** do computador local, clique com o botão direito do mouse no certificado que você está exportando. **Selecione Todas as Tarefas** no menu resultante e clique em **Exportar**.
    
&nbsp;&nbsp;&nbsp;i. No **Assistente para Exportação de Certificados**, clique em **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
   > [!NOTE]
   > Se **Sim, exportar** a chave privada não está disponível, então a chave privada desse certificado não foi marcada para exportação antes de você a ter. Você precisa solicitar o certificado do provedor novamente, com a chave privada definida para exportar, antes de fazer isso com êxito.
  
&nbsp;&nbsp;&nbsp;j. Na caixa de diálogo Exportar Formatos de Arquivo, selecione Informações Pessoais Exchange - PKCS#12 (. PFX) e selecione o seguinte:
    
 &nbsp;&nbsp;&nbsp;  i. Inclua todos os certificados no caminho de certificação, se possível.
    
 &nbsp;&nbsp;&nbsp;  ii. Exportar todas as propriedades estendidas.
    
   > [!NOTE]
   > **NUNCA** selecione **Excluir a chave privada se a exportação for bem-sucedida**. Isso significa que você terá que reaportar o certificado e a chave privada de volta para este Servidor de Borda.
  
&nbsp;&nbsp;&nbsp;k. Se você quiser atribuir uma senha para proteger a chave privada, digite uma senha para a chave privada. Reentra na senha para confirmar e clique em **Próximo**.
    
&nbsp;&nbsp;&nbsp;l. Digite um caminho e um nome de arquivo para o certificado exportado, usando uma extensão de arquivo **de .pfx**. O caminho precisa estar acessível pelos outros Servidores de Borda no pool ou você precisará mover o arquivo por meio de mídia externa (como uma unidade USB). Clique **em Próximo** quando você fez sua escolha.
    
&nbsp;&nbsp;&nbsp;m. Revise o resumo na caixa **de diálogo Concluindo o Assistente** de Exportação de Certificados e clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;n. Clique em **OK** na caixa de diálogo da exportação com sucesso.
    
&nbsp;&nbsp;&nbsp;o. Agora você precisará voltar para a seção Importar o certificado antes disso e importar o certificado para todos os Seus Servidores de Borda restantes e, em seguida, prosseguir com a atribuição, abaixo.
    
 
### <a name="4-assign-the-certificate"></a>4. Atribua o certificado

&nbsp;&nbsp;&nbsp;a. Em **CADA** Servidor de Borda, no Assistente de Implantação, ao lado da **Etapa 3. Solicitar, Instalar ou Atribuir Certificados,** clique **em Executar novamente**.
    
&nbsp;&nbsp;&nbsp;b. Na página **Tarefas de Certificados Disponíveis,** clique em **Atribuir um certificado existente.**
    
&nbsp;&nbsp;&nbsp;c. Na página **Atribuição de** Certificado, selecione **Borda Externa** na lista.
    
&nbsp;&nbsp;&nbsp;d. Na página **Armazenamento de** Certificados, selecione o certificado importado para a Borda externa (da seção anterior).
    
&nbsp;&nbsp;&nbsp;e. Na página **Resumo de Atribuição de** Certificado, procure as configurações e clique em Próximo **para** atribuir o certificado.
    
&nbsp;&nbsp;&nbsp;f. Na página de conclusão do assistente, clique em **Concluir**.
    
&nbsp;&nbsp;&nbsp;g. Depois de concluir esse procedimento, é realmente uma boa ideia abrir o snap-in MMC certificados em cada servidor, expandir **Certificados (computador local),** expandir **Pessoal,** clicar em **Certificados** e confirmar se o certificado de Borda interno está listado no painel de detalhes.
    
   > [!NOTE]
   > Você também terá que configurar os certificados para seu servidor proxy reverso. 
  
## <a name="starting-the-edge-servers"></a>Iniciando os Servidores de Borda

Depois que a instalação for concluída, você precisará iniciar os serviços em cada servidor de Borda em sua implantação:
  
1. Em cada Servidor de Borda, no Assistente **de** Implantação , ao lado da **Etapa 4: Iniciar Serviços,** clique em **Executar**.
    
2. Na página **Iniciar Skype for Business Server Serviços,** revise a lista de serviços e clique **em Próximo** para iniciar os serviços.
    
3. Depois que os serviços são iniciados, você pode clicar **em Concluir** para fechar o assistente.
    
4. (Opcional) Ainda em **Etapa 4: Iniciar Serviços,** clique em **Status dos Serviços.**
    
5.  No **MMC de Serviços** em cada servidor, verifique se todos os serviços Skype for Business Server estão sendo executados.
    

