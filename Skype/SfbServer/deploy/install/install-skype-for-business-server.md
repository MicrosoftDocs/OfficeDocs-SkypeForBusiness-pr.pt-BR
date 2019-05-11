---
title: Instalar o Skype for Business Server em servidores na topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Resumo: Saiba como instalar o Skype para componentes de sistema do servidor de negócios em cada servidor na topologia. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 130e8f2d0b14215c229bb78819ff072217a24b06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891814"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar o Skype for Business Server em servidores na topologia
 
**Resumo:** Saiba como instalar o Skype para componentes de sistema do servidor de negócios em cada servidor na topologia. Baixe uma versão de avaliação gratuita do Skype para Business Server a partir do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Depois que a topologia é carregada no repositório de gerenciamento Central e o Active Directory sabe quais servidores executarão quais funções, você precisará instalar o Skype para system Business Server em cada um dos servidores na topologia. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. Instalar o Skype para system Business Server é a etapa 7 de 8.
  
![Diagrama de visão geral.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instale o Skype para o sistema de Business Server

Depois de publicar uma topologia, você pode instalar o Skype para componentes de servidor de negócios em cada servidor na topologia. Esta seção o orienta através de instalando Skype para Business Server e configurando as funções de servidor para o pool de Front-End e qualquer funções de servidor forem colocadas com servidores Front-End. Para instalar e configurar funções de servidor, você pode executar o Skype para o Assistente de implantação de servidor de negócios em cada computador no qual você está instalando uma função de servidor. Você usará o Assistente de Implantação para completar as quatro etapas de implantação (instalação do repositório de configuração local, instalação dos servidores front-end, configuração dos certificados e inicialização dos serviços).
  
> [!IMPORTANT]
> Você deve usar o construtor de topologias para concluir e publique a topologia antes de instalar o Skype para Business Server nos servidores. 
  
> [!NOTE]
> Esse procedimento deve ser concluído em todos os servidores da topologia. 
  
> [!CAUTION]
> Após instalar o Skype para Business Server em um servidor Front-End, na primeira vez que você iniciar os serviços, você deve garantir que o serviço de Firewall do Windows está executando no servidor. 
  
> [!CAUTION]
> Antes de seguir estas etapas, certifique-se de que você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e membro do grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Se você ainda não executar Skype para a instalação do servidor de negócios neste servidor antes, você será solicitado para uma unidade e o caminho para a instalação. Com isso, a instalação poderá ser feita em uma unidade diferente da unidade do sistema, se a sua organização assim exigir ou se você tiver problemas de espaço. Você pode alterar o caminho do local de instalação para o Skype para arquivos do servidor de negócios na caixa de diálogo **Configurar** para uma nova unidade disponível. Se você instalar os arquivos de instalação para esse caminho, incluindo Ocscore, o restante do Skype para arquivos Business Server será implantado lá.
  
> [!IMPORTANT]
> Antes de começar a instalação, certifique-se de que o Windows Server seja atualizada usando o Windows Update. 
  
![Windows Server até a data.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instale o Skype para o sistema de Business Server

1. Insira o Skype para a mídia de instalação do servidor de negócios. Se a instalação não começar automaticamente, clique duas vezes em **Instalar**.
    
2. A mídia de instalação requer o Microsoft Visual C++ para ser executada. Uma caixa de diálogo aparecerá perguntando se você quer instalá-lo. Clique em **Sim.**
    
3. Leia com atenção o Contrato de Licença e se você estiver de acordo, selecione **Aceito os termos do contrato de licença** e clique em **OK**. 
    
4. Instalação inteligente é um recurso do Skype para Business Server onde você pode conectar à Internet para verificar as atualizações do Microsoft Update (MU) durante o processo de instalação, conforme mostrado na figura. Esse recurso proporciona uma experiência aprimorada, pois verifica se você tem as atualizações mais recentes do produto. Clique em **Instalar** para começar a instalação.
    
    > [!NOTE]
    > Muitas organizações têm o Windows Server Update Services (WSUS) implantado em seus ambientes empresariais. O WSUS permite que os administradores gerenciem completamente a distribuição de atualizações que são lançadas pelo Microsoft Update para computadores na sua rede. Como parte da versão de atualização cumulativa 1 Skype para Business Server introduziu suporte para a configuração inteligente funcionar com o WSUS. Clientes com o WSUS que estão implantando Skype para Business Server pela primeira vez ou atualizando do ambiente do Lync Server 2013 usando o recurso de atualização In-loco terão configuração inteligente buscando atualizações Skype para Windows do WSUS em vez de busca de atualizações do MU. Os clientes que desejarem usar o Smart Setup precisam executar o SmartSetupWithWSUS.psq em todos os computadores antes de executar o setup.exe. 
  
     ![Captura de tela de instalação inteligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Na página Assistente para implantação, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**.
    
6. Execute os procedimentos nos procedimentos a seguir, quando tiver concluído-los, clique em **Sair** para fechar o Assistente de implantação. Repita os procedimentos para cada Servidor Front-End no pool.
    
### <a name="step-1-install-local-configuration-store"></a>Etapa 1: instalar repositório de configuração local

1. Leia os pré-requisitos e clique em **Executar** ao lado de **Etapa 1: instalar repositório de configuração local**.
    
    > [!NOTE]
    > O repositório de configuração local é uma cópia somente leitura do Repositório de Gerenciamento Central. Em uma implantação da Standard Edition, o Repositório de Gerenciamento Central é criado usando uma cópia local do SQL Server Express Edition no servidor front-end quando você executa o procedimento Preparar primeiro servidor Standard Edition. Em uma implantação da Enterprise Edition, o Repositório de Gerenciamento Central é criado quando você publica a topologia que inclui um pool de front-ends da Enterprise Edition. 
  
2. Na página **Instalar Configurações de Armazenamento Local**, verifique se a opção **Recuperar diretamente do repositório de Gerenciamento Central** está selecionada, e clique em **Próximo**.
    
    O SQL Server Express Edition é instalado no servidor local. O SQL Server Express Edition é obrigatório para o repositório de configuração local.
    
3. Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Etapa 2: Configurar ou remover Skype para componentes de servidor de negócios

1. Revise os pré-requisitos e clique em **Executar** próximo a **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**.
    
2. Na página **Definir backup Skype para componentes de servidor de negócios** , clique em **Avançar** para definir os componentes conforme definido na sua topologia publicada.
    
3. A página **Executando Comandos** exibirá um resumo dos comandos e das informações de instalação durante a instalação. Quando estiver pronto, você pode usar a lista para selecionar um log para exibir e, em seguida, clique em **Exibir Log**.
    
4. Quando Skype para a instalação dos componentes do servidor de negócios é feito e você examinou os logs conforme necessário, clique em **Concluir** para concluir esta etapa na sua instalação.
    
    > [!NOTE]
    > Reinicie o servidor se for solicitado (o que pode acontecer se for necessário instalar a experiência desktop do Windows). Quando o computador back estiver em execução, você precisa executar este procedimento (etapa 2: instalar ou remover Skype para componentes de servidor de negócios) procedimento novamente. 
  
    > [!NOTE]
    > Se o instalador encontrar qualquer pré-requisito que não atendido, você será notificado com uma mensagem "Pré-requisito não atendido", conforme mostra a figura. Atender o pré-requisito necessário e inicie esse (etapa 2: instalar ou remover Skype para componentes de servidor de negócios) procedimento novamente. 
  
     ![Pré-requisito necessário.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Verifique se as duas primeiras etapas foram concluídas conforme o esperado. Verifique se há uma marca de seleção verde com a palavra **Concluído** conforme mostra a figura.
    
     ![Primeiro duas etapas concluídas desde a instalação de componentes.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Execute o **Windows Update** novamente para verificar se há atualizações depois de instalar o Skype para componentes de servidor de negócios.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Etapa 3: Solicitar, instalar ou atribuir certificados

1. Leia os pré-requisitos e clique em **Executar** ao lado de **Etapa 3: solicitar, instalar ou ceder certificados**.
    
    > [!NOTE]
    > Skype para Business Server inclui o suporte para o pacote de SHA-2 (SHA-2 usa digest comprimentos de 224, 256, 384 ou 512 bits) de hash digest e algoritmos de conexões de clientes executando o Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows de assinatura Server 2012, ou sistemas operacionais Windows Server 2008 R2. Para suportar o acesso externo usando o pacote do SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com a mesma extensão de disco. 
  
    > [!IMPORTANT]
    > A seleção do resumo do hash e do algoritmo de assinatura dependerá do cliente e dos servidores que utilizarão o certificado, e de outros computadores e dispositivos que os clientes e servidores comunicarão a quem também deve saber como usar os algoritmos usados no certificado. Para obter informações sobre qual digest comprimentos são suportados no sistema operacional e alguns aplicativos de cliente, consulte o [blog de PKI do Windows - SHA2 e Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Cada servidor front-end ou Standard Edition exige até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web. No entanto, é possível solicitar e atribuir um único certificado padrão com as entradas de nome de assunto alternativo, assim como o certificado oAuthTokenIssuer. Para obter detalhes sobre os requisitos de certificado, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > O seguinte procedimento descreve como configurar certificados a partir de uma autoridade de certificado baseada nos Serviços de Certificados do Active Directory. 
  
2. Na página **Assistente de Certificados**, clique em **Solicitar**.
    
3. Na página **Solicitação de Certificados** preencha os dados relevantes, incluindo seleção do domínio SIP e clique em **Avançar**.
    
4. Na página **Solicitações Atrasadas ou Imediatas**, é possível aceitar a opção padrão **Enviar a solicitação imediatamente para uma autoridade de certificação online** clicando em **Avançar**. A AC interna com inscrição online automática precisa estar disponível se você selecionar essa opção. Se você escolher a opção para atrasar a solicitação, receberá uma solicitação para fornecer um nome e local para salvar o arquivo de solicitação do certificado. A solicitação de certificado precisa ser apresentada a processada por uma AC dentro de sua organização ou por uma AC pública. Em seguida, será necessário importar a resposta do certificado e atribuí-la à função de certificado apropriada.
    
5. Na página **Escolher uma autoridade de certificação (CA)** , selecione a opção de **Selecionar uma autoridade de certificação na lista detectada em seu ambiente** e selecione um conhecido (por meio do registro nos serviços de domínio Active Directory) autoridade de certificação da lista. Como alternativa, selecione a opção **Especificar outra autoridade de certificação**, digite o nome de outra AC na caixa e clique em **Avançar**.
    
6. Na página **Conta da Autoridade de Certificação**, você deve informar as credenciais para solicitar e processar a solicitação de certificado na AC. Você deve determinar com antecedência se um nome de usuário e uma senha são necessários para solicitar um certificado. O administrador da AC terá as informações necessárias, e talvez seja necessário que ele ajude você nessa etapa. Se precisar fornecer credenciais alternativas, marque a caixa de seleção, digite um nome de usuário e uma senha nas caixas de texto e clique em **Avançar**.
    
7. Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo de Servidor da web padrão, clique em **Avançar**.
    
    > [!NOTE]
    > Se sua organização tiver criado um modelo para ser usado como uma alternativa para o modelo de AC padrão do Servidor da web, marque a caixa de seleção, e digite o nome do modelo alternativo. Você precisará do nome do modelo, conforme definido pelo administrador de AC. 
  
8. Na página **nome e configurações de segurança** , especifique um **Nome amigável**. Usando um nome amigável, você pode identificar rapidamente o certificado e a finalidade. Se você deixar em branco, um nome será gerado automaticamente. Definir o **comprimento de Bit** da chave ou aceite o padrão de 2048 bits. Selecione a **marcar a chave privada do certificado como exportável** se achar que a chave particular e o certificado precisa ser movido ou copiadas para outros sistemas e, em seguida, clique em **Avançar**.
    
    > [!NOTE]
    > Skype para Business Server tem requisitos mínimos de uma chave privada exportável. Um exemplo disso são os Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez de certificados individuais para cada instância no pool. 
  
9. Na página **Informações da Organização**, forneça, opcionalmente, as informações da organização e clique em **Avançar**.
    
10. Na página **Informações Geográficas**, forneça, opcionalmente, informações geográficas e clique em **Avançar**.
    
11. Na página **Nome da Entidade/Nomes Alternativos da Entidade**, revise os nomes alternativos da entidade que serão adicionados e clique em **Avançar**.
    
12. Na página **Configuração do Domínio SIP**, selecione o **Domínio SIP** e clique em **Avançar**.
    
13. Na página **Configurar Nomes Alternativos da Entidade Adicionais**, adicione quaisquer nomes alternativos da entidade adicionais necessários, incluindo qualquer um que possa ser exigido para domínios SIP adicionais no futuro, e clique em **Avançar**.
    
14. Na página **Resumo da Solicitação de Certificado**, revise as informações no resumo. Se as informações estiverem corretas, clique em **Avançar**. Se você precisar corrigir ou modificar uma configuração, clique em **Voltar** para a página apropriada a fim de fazer a correção ou modificação.
    
15. Na página **Executando Comandos**, clique em **Avançar**.
    
16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. Se ele é relatado como tendo sido emitido e instalado, mas não é válida, certifique-se de que o certificado raiz da autoridade de certificação foi instalado no repositório de autoridade de certificação de raiz confiáveis do servidor. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. Por padrão, a caixa de seleção para **atribuir o certificado para Skype para usos de certificado de servidor de negócios** está selecionada. If you want to manually assign the certificate, clear the check box, and then click **Finish**.
    
17. Se você ter desmarcado a caixa de seleção para **atribuir o certificado para Skype para usos de certificado de servidor de negócios** na página anterior, você será apresentada com a página de **Atribuição de certificado** . Click **Next**.
    
18. Na página **Repositório de Certificados**, selecione o certificado que você solicitou. Se você quiser ver o certificado, clique em **Exibir Detalhes do Certificado** e clique em **Avançar** para continuar.
    
    > [!NOTE]
    > Se a página **Status da Solicitação de Certificado Online** informar um problema com o certificado, como um certificado inválido, a exibição do certificado pode obter ajuda e resolver o problema. Dois problemas específicos que podem fazer com que um certificado seja inválido são a ausência o certificado AC raiz confiável, mencionada anteriormente, e a ausência de uma chave privada associada ao certificado. Consulte a documentação da AC para resolver esses dois problemas.
  
19. Na página **Resumo de Atribuição de Certificado**, examine as informações apresentadas a fim de assegurar que esse certificado deve ser atribuído e clique em **Avançar**.
    
20. Na página **Executando Comandos**, revise a saída do comando. Clique em **Exibir Log** se você quiser revisar o processo de atribuição ou se houver um erro ou aviso. Após a conclusão da revisão, clique em **Concluir**.
    
21. Na página **Assistente de Certificados**, verifique se todos os serviços têm uma marca de seleção verde indicando que há um certificado atribuído a eles, incluindo o OAuthTokenIssuer, conforme mostra a figura, e clique em **Fechar**.
    
     ![Os certificados instalados e atribuído corretamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Se estiver instalando em um ambiente de laboratório e tiver configurado a autoridade de certificação usando os Serviços de Certificados do Active Directory, você terá que reiniciar o servidor que está executando os serviços de certificados e o servidor front-end para que a atribuição de certificados seja concluída com sucesso. 
  
    > [!TIP]
    >  Para obter mais informações sobre certificados nos serviços de certificado do Active Directory, consulte [Serviços de certificados do Active Directory](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Etapa 4: iniciar serviços

1. Examine os pré-requisitos para a **Etapa 4: iniciar serviços**.
    
2. If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet. Se um único servidor for usado, que é sempre o caso com o Standard Edition, você se pergunta use o cmdlet **Start-CsWindowsService** . Neste exemplo, estamos usando Enterprise Edition com três servidores Front-End do pool, abra o **Skype para Business Server Management Shell** e execute o cmdlet **Start-CsPool** , conforme mostrado na figura. For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**. To deploy roles other than the Front End role, see documentation for those particular roles.
    
     ![Inicie o Skype para serviços corporativos.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Na página **Executando comandos**, depois que todos os serviços forem iniciados com sucesso, clique em **Finalizar**.
    
    > [!IMPORTANT]
    > O comando para iniciar os serviços no servidor é um método de esforço melhor para relatar que os serviços foram iniciados de fato. Ele pode não refletir o estado real do serviço. Recomendamos que você use a etapa **Status do serviço (opcional)** para abrir o MMC (Console de Gerenciamento da Microsoft) e verificar se os serviços foram iniciados com êxito, conforme mostra a figura. Se qualquer Skype para serviço de Business Server não foi iniciada, você pode se service no MMC do mouse em e, em seguida, clique em **Iniciar**. 
  
     ![Verifique se os serviços foram iniciados.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

