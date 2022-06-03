---
title: Instalar Skype for Business Server em servidores na topologia
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Resumo: saiba como instalar os componentes Skype for Business Server sistema em cada servidor na topologia.'
ms.openlocfilehash: 7aea6d25edcd28ba611b81d33eceed4172019bee
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860612"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype for Business Server em servidores na topologia
 
**Resumo:** Saiba como instalar os componentes Skype for Business Server sistema em cada servidor na topologia.
  
Depois que a topologia for carregada no Repositório de Gerenciamento Central e o Active Directory souber quais servidores executarão quais funções, você precisará instalar o sistema Skype for Business Server em cada um dos servidores na topologia. Você pode executar as etapas de 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. Instalar o sistema Skype for Business Server é a etapa 7 de 8.
  
![Diagrama de visão geral.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar Skype for Business Server sistema

Depois de publicar uma topologia, você pode instalar os Skype for Business Server em cada servidor na topologia. Esta seção orienta você pela instalação Skype for Business Server e configuração das funções de servidor para o pool de Front-Ends e todas as funções de servidor que são colocadas com os servidores Front-End. Para instalar e configurar funções de servidor, execute o Assistente Skype for Business Server implantação em cada computador no qual você está instalando uma função de servidor. Use o Assistente de Implantação para concluir todas as quatro etapas de implantação, incluindo a instalação do repositório de Configuração Local, a instalação dos Servidores Front-End, a configuração de certificados e a inicialização de serviços.
  
> [!IMPORTANT]
> Você deve usar o Construtor de Topologias para concluir e publicar a topologia antes de instalar Skype for Business Server em servidores. 
  
> [!NOTE]
> Esse procedimento deve ser concluído para todos os servidores na topologia. 
  
> [!CAUTION]
> Depois de instalar Skype for Business Server em um Servidor Front-End, na primeira vez que iniciar os serviços, verifique se o Serviço de Firewall do Windows está em execução no servidor. 
  
> [!CAUTION]
> Antes de seguir essas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Se você ainda não tiver executado Skype for Business Server configuração neste servidor antes, será solicitada uma unidade e um caminho para a instalação. Isso fornece a capacidade de instalar em uma unidade diferente da unidade do sistema, se sua organização a exigir ou se você tiver preocupações de espaço. Você pode alterar o caminho do local de instalação para os Skype for Business Server arquivos na caixa de  diálogo Instalação para uma nova unidade disponível. Se você instalar os arquivos de Instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos de Skype for Business Server serão implantados lá também.
  
> [!IMPORTANT]
> Antes de começar a instalação, verifique se Windows Server está atualizado usando Windows Update. 
  
![Windows servidor atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar Skype for Business Server sistema

1. Insira a mídia Skype for Business Server de instalação. Se a configuração não começar automaticamente, clique duas vezes em **Instalação**.
    
2. A mídia de instalação Microsoft Visual C++ ser executada. Uma caixa de diálogo será exibida perguntando se você deseja instalá-la. Clique **em Sim.**
    
3. Examine cuidadosamente o Contrato de Licença e, se você concordar, selecione **Aceitar** os termos no contrato de licença e clique em **OK**. 
    
4. A Configuração Inteligente é um recurso no Skype for Business Server em que você pode se conectar à Internet para verificar se há atualizações do Microsoft Update (MU) durante o processo de instalação, conforme mostrado na figura. Isso proporciona uma experiência melhor, fazendo com que você tenha as atualizações mais recentes do produto. Clique em **Instalar** para iniciar a instalação.
    
    > [!NOTE]
    > Muitas organizações Windows Server Update Services (WSUS) implantadas em seus ambientes corporativos. O WSUS permite que os administradores gerenciem totalmente a distribuição de atualizações lançadas por meio do Microsoft Update para computadores em sua rede. Como parte da versão da Atualização Cumulativa 1, Skype for Business Server suporte para a Instalação Inteligente funcionar com o WSUS. Os clientes com o WSUS que estão implantando o Skype for Business Server pela primeira vez ou atualizando do ambiente do Lync Server 2013 usando o recurso de Atualização do In-Place terão a Instalação Inteligente buscando Skype para atualizações do Windows do WSUS em vez de buscar atualizações do MU. Os clientes que desejam usar a Instalação Inteligente precisam executar o SmartSetupWithWSUS.psq em todos os computadores antes de executar Setup.exe. 
  
     ![Captura de tela da Configuração Inteligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Na página Assistente de Implantação, clique **em Instalar ou Atualizar Skype for Business Server Sistema**.
    
6. Execute os procedimentos nos procedimentos a seguir, quando tiver concluído, clique em **Sair** para fechar o Assistente de Implantação. Repita os procedimentos para cada servidor Front-End no pool.
    
### <a name="step-1-install-local-configuration-store"></a>Etapa 1: Instalar o Repositório de Configurações Local

1. Examine os pré-requisitos e clique em **Executar** ao lado **da Etapa 1: Instalar o Repositório de Configurações Local**.
    
    > [!NOTE]
    > O Repositório de Configurações Local é uma cópia somente leitura do Repositório de Gerenciamento Central. Em uma Edição Standard, o Repositório de Gerenciamento Central é criado usando uma cópia local do SQL Server Express Edition no servidor Front-End. Isso acontece quando você executa o procedimento Preparar Primeiro Edição Standard Servidor. Em uma Edição Enterprise, o repositório de Gerenciamento Central é criado quando você publica a topologia que inclui um pool Edição Enterprise front-end. 
  
2. Na página **Instalar Repositório de Configurações Local** , verifique se a opção Recuperar diretamente do repositório de Gerenciamento **Central** está selecionada e clique em **Avançar**.
    
    SQL Server Express Edition está instalado no servidor local. SQL Server Express Edition é necessária para o repositório de configuração local.
    
3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.
    
### <a name="step-2-set-up-or-remove-skype-for-business-server-components"></a>Etapa 2: Configurar ou remover Skype for Business Server componentes

1. Examine os pré-requisitos e clique em Executar ao  lado da Etapa **2: Configurar ou Remover Skype for Business Server Componentes**.
    
2. Na página **Configurar Skype for Business Server Componentes**, clique em Avançar para configurar  componentes conforme definido em sua topologia publicada.
    
3. A **página Comandos em** Execução exibe um resumo de comandos e informações de instalação conforme a configuração ocorre. Quando terminar, você poderá usar a lista para selecionar um log a ser visualizado e, em seguida, clicar em **Exibir Log**.
    
4. Quando Skype for Business Server instalação dos componentes for concluída e você tiver revisado os logs conforme necessário, clique em Concluir para  concluir esta etapa na instalação.
    
    > [!NOTE]
    > Reinicie o servidor, se solicitado (o que pode acontecer se Windows experiência de área de trabalho precisar ser instalada). Quando o computador estiver funcionando novamente, você precisará executar este procedimento (Etapa 2: Configurar ou Remover Skype for Business Server Componentes) novamente. 
  
    > [!NOTE]
    > Se o instalador encontrar os pré-requisitos que não foram atendidos, você será notificado com uma mensagem "Pré-requisito não atendido", conforme mostrado na figura. Atenda ao pré-requisito necessário e, em seguida, inicie este procedimento (Etapa 2: Configurar ou remover Skype for Business Server componentes) novamente. 
  
     ![Pré-requisito necessário.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Verifique se as duas primeiras etapas foram concluídas conforme o esperado. Confirme se há uma marca de seleção verde com a palavra **Concluir**, conforme mostrado na figura.
    
     ![As duas primeiras etapas foram concluídas da instalação de componentes.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Execute **Windows Update** novamente para verificar se há atualizações depois de instalar o Skype for Business Server Componentes.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Etapa 3: Solicitar, instalar ou atribuir certificados

1. Examine os pré-requisitos e clique em Executar ao  lado da Etapa **3: Solicitar, Instalar ou Atribuir Certificados**.
    
    > [!NOTE]
    > Skype for Business Server inclui suporte para o pacote SHA-2 (SHA-2 usa comprimentos de resumo de 224, 256, 384 ou 512 bits) de algoritmos de hash de resumo e assinatura para conexões de clientes que executam o Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 ou sistemas operacionais Windows Server 2008 R2. Para dar suporte ao acesso externo usando o pacote SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com o mesmo resumo de comprimento de bit. 
  
    > [!IMPORTANT]
    > A seleção de qual resumo de hash e algoritmo de assinatura depende dos clientes e dos servidores que usarão o certificado e de outros computadores e dispositivos com os quais os clientes e servidores se comunicarão, que também devem saber como usar os algoritmos usados no certificado. Para obter informações sobre quais comprimentos de resumo têm suporte no sistema operacional e alguns aplicativos cliente, consulte Windows [blog PKI – SHA2 e Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Cada Edição Standard ou servidor Front-End requer até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web. No entanto, você pode solicitar e atribuir um único certificado padrão com entradas de nome alternativo de entidade apropriadas, bem como o certificado oAuthTokenIssuer. Para obter detalhes sobre os requisitos de certificado, consulte [Requisitos ambientais para Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > O procedimento a seguir descreve como configurar certificados de uma autoridade de certificação interna baseada nos Serviços de Certificados do Active Directory. 
  
2. Na página **Assistente de Certificados**, clique em **Solicitar**.
    
3. Na página **Solicitação de** Certificado, preencha os dados relevantes, incluindo a seleção do domínio SIP e clique em **Avançar**.
    
4. Na página **Solicitações Atrasadas** ou Imediatas, você pode aceitar o padrão Enviar a solicitação imediatamente para uma opção de autoridade de certificação **online** clicando em **Avançar**. A AC interna com registro online automático deverá estar disponível se você selecionar essa opção. Se você escolher a opção para atrasar a solicitação, será solicitado um nome e um local para salvar o arquivo de solicitação de certificado. A solicitação de certificado deve ser apresentada e processada por uma AC dentro de sua organização ou por uma AC pública. Em seguida, você precisará importar a resposta do certificado e atribuí-la à função de certificado adequada.
    
5. Na página Escolher uma AC **(** Autoridade de Certificação), selecione Selecionar  uma AC na lista detectada na opção de ambiente e, em seguida, selecione uma AC conhecida (por meio do registro no Active Directory Domain Services) na lista. Ou selecione a **opção Especificar outra autoridade de certificação** , insira o nome de outra AC na caixa e clique em **Avançar**.
    
6. Na página **Conta da Autoridade de Certificação**, são solicitadas credenciais para solicitar e processar a solicitação de certificado na AC. Você deve ter determinado se um nome de usuário e senha são necessários para solicitar um certificado antecipadamente. O administrador da AC terá as informações necessárias e talvez tenha que ajudá-lo nesta etapa. Se for necessário fornecer credenciais alternativas, selecione a opção, forneça um nome de usuário e senha nas caixas de texto e clique em **Avançar**.
    
7. Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo do Servidor Web padrão, clique em **Avançar**.
    
    > [!NOTE]
    > Se sua organização criou um modelo para uso como uma alternativa para o modelo padrão da AC do servidor Web, marque a caixa de seleção e insira o nome do modelo alternativo. Você precisará no nome de modelo conforme definido pelo administrador da AC. 
  
8. Na página **Nome e Segurança Configurações**, especifique um **Nome Amigável**. Usando um nome amigável, você pode identificar rapidamente o certificado e a finalidade. Se deixá-lo em branco, um nome será gerado automaticamente. Defina o **Comprimento de bit** da chave ou aceite o padrão de 2048 bits. Selecione Marcar a chave privada do certificado como **exportável** se você determinar que o certificado e a chave privada precisam ser movidos ou copiados para outros sistemas e clique em **Avançar**.
    
    > [!NOTE]
    > Skype for Business Server requisitos mínimos para uma chave privada exportável. Um local está nos Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez dos certificados individuais para cada instância no pool. 
  
9. Na página **Informações da Organização** , opcionalmente, forneça informações da organização e clique em **Avançar**.
    
10. Na página **Informações Geográficas** , opcionalmente, forneça informações geográficas e clique em **Avançar**.
    
11. Na página **Nome da Entidade / Nomes Alternativos de Entidade**, veja os nomes alternativos de entidade que serão adicionados e clique em **Avançar**.
    
12. Na página **de configuração domínio SIP** , selecione o domínio **SIP** e clique em **Avançar**.
    
13. Na página **Configurar** Nomes Alternativos de Entidade Adicional, adicione outros nomes alternativos de assunto necessários, incluindo qualquer um que possa ser necessário para domínios SIP adicionais no futuro e clique em **Avançar**.
    
14. Na página **Resumo da Solicitação de** Certificado, examine as informações no resumo. Se as informações estão corretas, clique em **Avançar**. Se você precisar corrigir ou modificar uma configuração, clique em **Voltar** para a página adequada para fazer a correção ou modificação.
    
15. Na página **Executando Comandos**, clique em **Avançar**.
    
16. Na página **Status da Solicitação de Certificado** Online, examine as informações retornadas. Você deve observar que o certificado foi emitido e instalado no repositório de certificados local. Se for relatado como tendo sido emitido e instalado, mas não for válido, verifique se o certificado raiz da AC foi instalado no repositório de AC raiz confiável do servidor. Consulte a documentação da AC sobre como recuperar um certificado de autoridade de certificação raiz confiável. Se você precisar exibir o certificado recuperado, clique em **Exibir Detalhes do Certificado**. Por padrão, a caixa de seleção Atribuir **o certificado Skype for Business Server usos de certificado está** selecionada. Se você quiser atribuir manualmente o certificado, desmarque a caixa de seleção e clique em **Concluir**.
    
17. Se você tiver desmarcado a caixa de seleção Atribuir o certificado **Skype for Business Server usos** de certificado na página anterior, você verá a página Atribuição **de** Certificado. Clique em **Avançar**.
    
18. Na página **Repositório de Certificados** , selecione o certificado solicitado. Se você quiser exibir o certificado, clique em **Exibir Detalhes do** Certificado e clique **em Avançar** para continuar.
    
    > [!NOTE]
    > Se a **página Status da** Solicitação de Certificado Online tiver relatado um problema com o certificado, como se o certificado não fosse válido, exiba o certificado real para obter ajuda para resolver o problema. Dois problemas específicos que podem fazer com que um certificado não seja válido é o certificado de AC raiz confiável mencionado anteriormente e uma chave privada ausente associada ao certificado. Consulte a documentação da AC para resolver esses dois problemas.
  
19. Na página **Resumo da Atribuição de** Certificado, examine as informações apresentadas para verificar se esse é o certificado que deve ser atribuído e clique em **Avançar**.
    
20. Na página **Comandos em Execução** , examine a saída do comando. Clique **em Exibir Log** se quiser examinar o processo de atribuição ou se houver um erro ou aviso emitido. Quando terminar a revisão, clique em **Concluir**.
    
21. Na página  Assistente de Certificado, confirme se todos os serviços têm uma verificação verde para indicar que todos foram atribuídos a um certificado, incluindo o OAuthTokenIssuer, conforme mostrado na figura e clique em **Fechar.**
    
     ![Certificados instalados e atribuídos corretamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Se você estiver instalando em um ambiente de laboratório e acabou de configurar a Autoridade de Certificação usando os Serviços de Certificados do Active Directory, será necessário reinicializar o servidor que executa os Serviços de Certificados e também o servidor Front-End antes que a atribuição de certificado possa ser executada com êxito. 
  
    > [!TIP]
    >  Para obter mais informações sobre certificados nos Serviços de Certificados do Active Directory, consulte [Serviços de Certificados do Active Directory](/windows/deployment/deploy-whats-new). 
  
### <a name="step-4-start-services"></a>Etapa 4: Iniciar Serviços

1. Examine os pré-requisitos da **Etapa 4: Iniciar Serviços**.
    
2. Se esse for um pool Edição Enterprise front-end com pelo menos três servidores, Windows Fabric será usado e você deverá usar o cmdlet **Start-CsPool**. Se um único servidor for usado, que é sempre o caso com Edição Standard, você usará o cmdlet **Start-CsWindowsService**. Neste exemplo, estamos usando o Edição Enterprise com três servidores Front-End no pool, abra o Shell de Gerenciamento do **Skype for Business Server** e execute o cmdlet **Start-CsPool**, conforme mostrado na figura. Para todas as outras funções, incluindo Edição Standard servidor, você deve usar **Start-CsWindowsService**. Para implantar funções diferentes da função front-end, consulte a documentação dessas funções específicas.
    
     ![Inicie Skype for Business serviços.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Na página **Executando comandos**, após todos os serviços serem iniciados com sucesso, clique em **Finalizar**.
    
    > [!IMPORTANT]
    > O comando para iniciar os serviços no servidor é um método de melhor esforço para relatar que os serviços, na verdade, foram iniciados. Ele pode não refletir o estado real do serviço. Recomendamos que você use a etapa **Status** do Serviço (Opcional) para abrir o MMC (Console de Gerenciamento Microsoft) e confirmar se os serviços foram iniciados com êxito, conforme mostrado na figura. Se algum Skype for Business Server serviço não tiver sido iniciado, você poderá clicar com o botão direito do mouse nesse serviço no MMC e, em seguida, clicar em **Iniciar**. 
  
     ![Verifique se os serviços foram iniciados.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
