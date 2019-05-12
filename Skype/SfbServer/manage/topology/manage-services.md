---
title: Gerenciar serviços no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como exibir o status do serviço, iniciar e parar serviços e evitar sessões de serviços.
ms.openlocfilehash: 78d8b2a16204585a0ff403867617ff709666c4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911963"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gerenciar serviços no Skype para Business Server

Você pode usar o Skype para painel de controle do Business Server para exibir uma lista de todos os computadores que executam o Skype para Business Server em sua topologia, exibir o status dos serviços, iniciar ou parar serviços e evitar sessões de serviços.

- [Exibir uma lista de computadores que executam o Skype para Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Exibir o status dos serviços executados em um computador no Skype para negócios](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Iniciar ou parar Skype para serviços corporativos](#start-or-stop-skype-for-business-services)
- [Evitar sessões de serviços](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Exibir uma lista de computadores que executam o Skype para Business Server

Use o Skype para painel de controle do Business Server para exibir uma lista de todos os computadores que estão executando o Skype para negócios em sua topologia e ver o status do serviço de cada um. Você pode classificar a lista por computador, pool ou site. 

1. Usando uma conta de usuário atribuída a qualquer uma das funções administrativas predefinidas para Skype para Business Server, faça logon em qualquer computador em sua implantação interna. Para obter mais informações, consulte [o controle de acesso baseado em função (RBAC) para Skype para Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página Status, execute um dos seguintes conforme necessário:
    - Classifique a lista clicando em **computador**, **Pool**ou cabeçalho de coluna de **Site** e em seguida, clicando na seta para cima ou seta para baixo.
    - Clique em **Atualizar** para exibir a lista mais atualizada.
    - Procure um computador específico, digitando o nome do computador no campo de pesquisa.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Exibir o status dos serviços executados em um computador no Skype para negócios

Use o Skype para painel de controle do Business Server para exibir todos os serviços que estão sendo executados em um determinado computador em sua Skype para a topologia de servidor de negócios e ver o status de cada serviço.

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **topologia**.
4. Na página Status, classifique ou pesquise a lista conforme necessário para localizar o computador que você está interessado, e clique no nome do computador.
5. Siga um destes procedimentos:
    - Para ver o status mais recente dos serviços executados no computador, clique em **obter o status do serviço**.
    - Para ver uma lista de serviços específicos executados no computador e o status de cada serviço, clique em **Propriedades**e, em seguida, clique em **Fechar** para retornar à lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Exibindo o status de serviço usando Cmdlets do Windows PowerShell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet Get-CsWindowsService. Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. Para obter mais informações, consulte [Skype do Shell de gerenciamento do servidor de negócios](../management-shell.md).

**Para exibir o status do serviço**

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Skype do Shell de gerenciamento do servidor de negócios e pressione Enter:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Este comando retorna informações semelhantes para o seguinte:

```
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

Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Iniciar ou parar Skype para serviços corporativos

Use o Skype para painel de controle do Business Server para iniciar ou parar todos o Skype para serviços de Business Server em execução em um computador específico ou para iniciar ou parar um serviço específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar ou parar todos os Skype para serviços de Business Server em um computador

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server . Você pode determinar se você tiver atribuído a CsServerAdministrator ou a função CsAdministrator RBAC executando um comando semelhante ao seguinte:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página Status, classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando os serviços que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar ou parar um serviço específico

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página Status, classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.
7. Clique em **ação**.
8. Clique em **Iniciar serviço** ou **Parar o serviço**.
9. Clique em **Fechar**.


## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços

Use o Skype para painel de controle de negócios para impedir novas sessões para todos o Skype para serviços de Business Server em execução em um computador específico ou para impedir novas sessões para um serviço específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedir novas sessões para todos os Skype para serviços de Business Server em um computador

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página Status, classificação ou pesquisa através da lista como necessário para localizar o computador que está executando os serviços para o qual você deseja impedir novas sessões e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **impedir novas sessões para todos os serviços**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedir novas sessões para um serviço específico

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o Skype para painel de controle do Business Server, consulte [Install and abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Clique em **Propriedades**.
5. Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.
6. Clique em **ação**.
7. Clique em **impedir novas sessões para o serviço**.
8. Clique em **Fechar**.
