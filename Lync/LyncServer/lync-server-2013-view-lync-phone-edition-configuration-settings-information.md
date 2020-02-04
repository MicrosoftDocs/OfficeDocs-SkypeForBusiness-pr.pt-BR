---
title: 'Lync Server 2013: exibir informações sobre as configurações de configuração do Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Exibir as informações de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode exibir informações de configuração sobre os dispositivos que executam o Lync Phone Edition. As informações são organizadas em coleções. Ao instalar o Lync Server, você obtém uma coleção de configurações do Lync Phone Edition que se aplicam a todos os dispositivos que executam o Lync Phone Edition na sua implantação. Você também pode criar novos conjuntos de configurações para um site específico. As configurações do site têm precedência sobre as configurações globais. Cada conjunto de configurações consiste em um nome, o escopo (global ou de site), a configuração de segurança SIP, o nível de log, o nível de qualidade do serviço (QoS), a configuração de bloqueio de telefone e os detalhes do bloqueio de telefone, ou seja, o comprimento mínimo da identificação pessoal de desbloquear número (PIN) e hora antes do telefone bloquear a si mesmo.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Para ver as informações de configuração sobre os dispositivos que executam o Lync Phone Edition

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de dispositivo** .

4.  Na página **configuração de dispositivo** , clique no conjunto de configurações sobre as quais você deseja ver informações. O nome, o escopo, a configuração de segurança SIP, o nível de qualidade de voz e a configuração de bloqueio de telefone são listados na página principal. Para ver os detalhes do nível de log e bloqueio de telefone, clique no menu **Editar** e em **Mostrar detalhes**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo as informações de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode exibir as configurações do Lync Phone Edition usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Para exibir as informações de configuração do Lync Phone Edition

  - Para ver informações sobre todas as suas configurações do Lync Phone Edition, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsUCPhoneConfiguration
    
    O comando retorna informações semelhantes às seguintes:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Excluir uma coleção existente de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Impor o bloqueio de telefone no Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

