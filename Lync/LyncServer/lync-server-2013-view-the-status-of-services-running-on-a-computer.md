---
title: 'Lync Server 2013: exibir o status dos serviços em execução em um computador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Exibir o status dos serviços em execução em um computador no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Você pode usar o painel de controle do Lync Server 2013 para exibir todos os serviços que estão sendo executados em um computador específico na sua topologia do Lync Server e ver o status de cada serviço.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para exibir o status dos serviços em execução em um computador

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **topologia**.

4.  Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador no qual você está interessado e, em seguida, clique no nome do computador.

5.  Execute qualquer uma das seguintes ações:
    
      - Para ver o status mais recente dos serviços em execução no computador, clique em **obter status do serviço**.
    
      - Para ver uma lista de serviços específicos em execução no computador e o status de cada serviço, clique em **Propriedades**e, em seguida, clique em **fechar** para retornar à lista.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualizando o status do serviço usando cmdlets do Windows PowerShell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet **Get-CsWindowsService** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-view-service-status"></a>Para exibir o status do serviço

  - Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Este comando retorna informações semelhantes para o seguinte:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

