---
title: Gerenciar aplicativos confiáveis
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server.
ms.openlocfilehash: 4164f00b787ac8f234d13ba7c31e54c79cb1efd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750160"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Gerenciar aplicativos confiáveis em Skype for Business Server

Um *aplicativo confiável* é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server. Para obter detalhes sobre aplicativos UCMA, consulte "Unified Communications Managed API 3.0 Core SDK Documentation" em https://go.microsoft.com/fwlink/p/?linkId=210320 .

Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio. 

Use este artigo para saber como configurar um novo servidor de aplicativos confiáveis, exibir uma lista de aplicativos confiáveis e exibir informações de aplicativos confiáveis. 

## <a name="configure-a-new-trusted-application-server"></a>Configurar um novo servidor de aplicativo confiável

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar Construtor de Topologias: clique em **Iniciar,** **clique** em Todos os Programas, Skype for Business Server **e** clique Skype for Business Server Construtor **de Topologias.**

3.  Selecione **Baixar topologia da implantação existente** e clique em **OK**.

4.  Na caixa **de diálogo Salvar Topologia Como,** clique no arquivo Construtor de Topologias que você deseja usar e clique em **Salvar**.

5.  No painel esquerdo, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo Pool de Aplicativos Confiáveis.**

6.  Insira o **FQDN do Pool** do pool de aplicativos confiável, selecione se será um servidor único ou vários servidores e clique em **Avançar**.

7.  Na página **Selecionar o próximo salto,** na lista, selecione o pool Skype for Business Server front-end.

8.  Clique em **Concluir**.

9.  Selecione o nó superior **Skype for Business Server** e, no menu **Ações,** clique em **Publicar Topologia**.
    
    O **Pool de Aplicativos Confiáveis** deve ter sido criado com êxito e associado ao pool de Front-End correto.


## <a name="view-a-list-of-trusted-applications"></a>Exibir uma lista de aplicativos confiáveis

Você pode usar o painel de Skype for Business Server para exibir uma lista dos aplicativos confiáveis que você implantou em seu ambiente Skype for Business Server ambiente. Um aplicativo confiável é um aplicativo baseado no Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK que é confiável pelo Skype for Business Server. Essa relação de confiança é resumida na lista a seguir:

  - Os aplicativos confiáveis não são desafiados para autenticação por Skype for Business Server.

  - Os aplicativos confiáveis não são Skype for Business Server para transações SIP, conexões ou chamadas VoIP (Voice over Internet Protocol) de saída.

  - Aplicativos confiáveis podem representar qualquer usuário e participar de conferências sem aparecer em lista.

  - Os aplicativos confiáveis são altamente disponíveis e resilientes.

No painel Skype for Business Server controle, você pode ver o nome dos aplicativos, o pool onde eles são executados e a porta que eles usam.


### <a name="to-view-a-list-of-trusted-applications"></a>Para exibir uma lista de aplicativos confiáveis

1.  Em uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinida disponíveis no Skype for Business Server, consulte Controle de acesso baseado em função [(RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3.  Na barra de navegação esquerda, clique em **Topologia** e clique em **Aplicativo Confiável.**

4.  Na página **Aplicativo Confiável,** clique em um título de coluna para classificar os aplicativos, se necessário.


## <a name="view-trusted-application-information"></a>Exibir informações de aplicativos confiáveis

Você pode exibir informações sobre seus aplicativos confiáveis usando Windows PowerShell e o cmdlet **Get-CsTrustedApplication.** Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Para ver aplicativos confiáveis

Para exibir todos os aplicativos confiáveis, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
   **Get-CsConferenceDisclaimer**
    
   Esse comando retorna informações semelhantes às seguintes para cada aplicativo confiável:
    
   Identidade : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Contatos do Aplicativo,Cn=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistradorPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName :<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   Habilitado : True<br/>
    
   Para detalhes, consulte [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).