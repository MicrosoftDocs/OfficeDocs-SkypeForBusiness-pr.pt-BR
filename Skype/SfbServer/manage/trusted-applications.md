---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Um aplicativo confiável é um aplicativo baseado no SDK do UCMA (Unified Communications Managed API) 3.0 Core da Microsoft que é confiável Skype for Business Server.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674533"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis no Skype for Business Server

Um *aplicativo confiável* é um aplicativo baseado no SDK do UCMA (Unified Communications Managed API) 3.0 Core da Microsoft que é confiável Skype for Business Server. Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core SDK Documentation" (Documentação do SDK do Unified Communications Managed API 3.0 Core) em https://go.microsoft.com/fwlink/p/?linkId=210320.

Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiável, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativo confiável

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Inicie o Construtor de Topologias **: clique** em Iniciar **, clique em** Todos os Programas, **Skype for Business Server** e, em seguida, clique **Skype for Business Server Construtor de Topologias**.

3.  Selecione **Baixar topologia da implantação existente** e clique em **OK**.

4.  Na caixa **de diálogo Salvar Topologia como** , clique no arquivo do Construtor de Topologias que você deseja usar e clique em **Salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **Servidores de** Aplicativos Confiáveis e clique em **Novo Pool de Aplicativos Confiáveis**.

6.  Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **Selecionar o próximo salto**, na lista, selecione o pool Skype for Business Server Front-End.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype for Business Server** e, em seguida, no menu **Ações**, clique em **Publicar Topologia**.
    
    O **Pool de Aplicativos** Confiáveis deve ter sido criado com êxito e associado ao pool de Front-Ends correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o Skype for Business Server Painel de Controle para exibir uma lista dos aplicativos confiáveis que você implantou em seu Skype for Business Server ambiente. Um aplicativo confiável é um aplicativo baseado no SDK do UCMA (Unified Communications Managed API) 3.0 Core da Microsoft que é confiável Skype for Business Server. Essa relação de confiança é resumida na lista a seguir:

  - Aplicativos confiáveis não são desafiados para autenticação por Skype for Business Server.

  - Os aplicativos confiáveis não são limitados por Skype for Business Server para transações SIP, conexões ou chamadas VoIP (Voice over Internet Protocol).

  - Aplicativos confiáveis podem representar qualquer usuário e ingressar em conferências sem aparecer em listas de participação.

  - Aplicativos confiáveis são altamente disponíveis e resilientes.

No Skype for Business Server Painel de Controle, você pode ver o nome dos aplicativos, o pool em que eles são executados e a porta que eles usam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Em uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte [RBAC (](../plan-your-deployment/security/role-based-access-control-rbac.md)controle de acesso baseado em função).

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle.

3.  Na barra de navegação à esquerda, clique **em Topologia** e, em seguida, clique **em Aplicativo Confiável**.

4.  Na página **Aplicativo Confiável** , clique em um título de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativo confiável

Você pode exibir informações sobre seus aplicativos confiáveis usando Windows PowerShell cmdlet **Get-CsTrustedApplication**. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicativos confiáveis

Para exibir todos os seus aplicativos confiáveis, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
   **Get-CsConferenceDisclaimer**
    
   Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:
    
   Identidade: CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool: 487279971<br/>
   HomeServer: CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber:<br/>
   LineURI:<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages: {}<br/>
   EnterpriseVoiceEnabled: True<br/>
   ExUmEnabled: False<br/>
   Habilitado: True<br/>
    
   Para detalhes, consulte [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).