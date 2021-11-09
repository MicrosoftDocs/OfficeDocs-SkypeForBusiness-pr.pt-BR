---
title: Gerenciar serviços em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Saiba como exibir o status do serviço, iniciar e interromper serviços e impedir sessões para serviços.
ms.openlocfilehash: cc5218f5347eb2124f42b8881bce730c74889bda
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864728"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gerenciar serviços em Skype for Business Server

Você pode usar o Painel de Controle Skype for Business Server para exibir uma lista de todos os computadores que estão executando Skype for Business Server em sua topologia, exibir o status dos serviços, iniciar ou interromper serviços e impedir sessões para serviços.

- [Exibir uma lista de computadores que executam Skype for Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Exibir o status dos serviços em execução em um computador em Skype for Business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Iniciar ou interromper Skype for Business serviços](#start-or-stop-skype-for-business-services)
- [Evitar sessões de serviços](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Exibir uma lista de computadores que executam Skype for Business Server

Use o Skype for Business Server painel de controle para exibir uma lista de todos os computadores que estão executando Skype for Business em sua topologia e veja o status de serviço de cada um. Você pode classificar a lista por computador, pool ou site. 

1. Em uma conta de usuário atribuída a qualquer uma das funções administrativas predefinida para Skype for Business Server, faça logoff em qualquer computador em sua implantação interna. Para obter mais informações, consulte Controle de acesso baseado em [função (RBAC) para Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.
4. Na página Status, faça o seguinte conforme necessário:
    - Classifique a lista clicando no título de coluna **Computador**, **Pool** ou **Site** e, em seguida, clicando na seta para cima ou seta para baixo.
    - Clique em **Atualizar** para exibir a lista mais atualizada.
    - Procure um computador específico, digitando o nome do computador no campo de pesquisa.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Exibir o status dos serviços em execução em um computador em Skype for Business

Use o Skype for Business Server de controle para exibir todos os serviços que estão sendo executados em um computador específico em sua topologia Skype for Business Server e veja o status de cada serviço.

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação esquerda, clique em **Topologia**.
4. Na página Status, classifique ou pesquise a lista conforme necessário para localizar o computador que deseja e clique no nome do computador.
5. Siga um destes procedimentos:
    - Para ver os status de serviços mais atuais executados no computador, clique em **Obter status de serviço**.
    - Para ver uma lista de serviços específicos executados no computador e o status de cada serviço, clique em **Propriedades** e em **Fechar** para retornar à lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Exibindo o status do serviço usando Windows PowerShell Cmdlets

Você também pode exibir o status do serviço usando Windows PowerShell e o cmdlet Get-CsWindowsService usuário. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter mais informações, [consulte Skype for Business Server Shell de Gerenciamento](../management-shell.md).

**Para exibir o status do serviço**

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de Gerenciamento Skype for Business Server e pressione Enter:

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Esse comando retornará informações parecidas com:

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Para obter detalhes, [consulte Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice).

## <a name="start-or-stop-skype-for-business-services"></a>Iniciar ou interromper Skype for Business serviços

Use o Skype for Business Server de controle para iniciar ou interromper todos os serviços Skype for Business Server em execução em um computador específico ou para iniciar ou interromper um serviço específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar ou interromper todos os Skype for Business Server em um computador

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server. Você pode determinar se foi atribuída a função CsServerAdministrator ou CsAdministrator RBAC executando um comando semelhante ao seguinte:

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.
4. Na página Status, classifique ou procure pela lista para encontrar o computador executando os serviços que você deseja iniciar ou parar e clique neles.
5. Clique em **Ação**.
6. Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar ou interromper um serviço específico

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.
4. Na página Status, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.
7. Clique em **Ação**.
8. Clique em **Iniciar serviço** ou **Parar serviço**.
9. Clique em **Fechar**.


## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços

Use o Skype for Business de controle para impedir novas sessões para todos os serviços Skype for Business Server em execução em um computador específico ou para impedir novas sessões para um serviço específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedir novas sessões para todos os serviços Skype for Business Server em um computador

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.
4. Na página Status, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.
5. Clique em **Ação**.
6. Clique em **Impedir novas sessões para todos os serviços**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedir novas sessões para um serviço específico

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle Skype for Business Server, consulte [Instalar e abrir ferramentas administrativas.](../../management-tools/install-and-open-administrative-tools.md)
3. Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.
4. Clique em **Propriedades**.
5. Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.
6. Clique em **Ações**.
7. Clique em **Impedir novas sessões para o serviço**.
8. Clique em **Fechar**.