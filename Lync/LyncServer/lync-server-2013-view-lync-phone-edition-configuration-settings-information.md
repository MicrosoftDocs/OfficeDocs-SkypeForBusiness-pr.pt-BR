---
title: 'Lync Server 2013: exibir informações de definições de configuração do Lync Phone Edition'
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
ms.openlocfilehash: db68b4612e2adb08a391d6ee3d8e590aefbb7a8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Exibir as informações de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode exibir informações de configuração sobre dispositivos que executam o Lync Phone Edition. As informações são organizadas em conjuntos. Ao instalar o Lync Server, você obtém uma coleção de configurações do Lync Phone Edition que se aplicam a todos os dispositivos que executam o Lync Phone Edition em sua implantação. Você também pode criar novos conjuntos de configurações para um site específico. As configurações de site tem precedência sobre configurações globais. Cada conjunto de configurações consiste em um nome, o escopo (global ou site), configuração de segurança SIP, nível de log, nível do QoS (Qualidade de Serviço) de voz, configuração de bloqueio de telefone e detalhes de bloqueio de telefone, isto é, o comprimento mínimo do PIN (número de identificação pessoal) de desbloqueio e o tempo para que o telefone se bloqueie sozinho.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Para exibir informações de configuração sobre dispositivos que executam o Lync Phone Edition

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes**, e então clique no botão de navegação **Configuração de Dispositivo**.

4.  Na página **Configuração de Dispositivo**, clique no conjunto de configurações sobre o qual deseja visualizar informações. O nome, escopo, configuração de segurança SIP, nível de qualidade de voz e a configuração de bloqueio de telefone são listados na página principal. Para visualizar o nível de log e os detalhes de bloqueio de telefone, clique no menu **Editar**, e então clique em **Exibir detalhes**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode exibir as definições de configuração do Lync Phone Edition usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Para exibir as informações de configuração do Lync Phone Edition

  - Para exibir informações sobre todas as suas definições de configuração do Lync Phone Edition, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsUCPhoneConfiguration
    
    O comando retorna informações parecidas com as seguintes:
    
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


[Criar ou modificar um conjunto de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Impor bloqueio de telefone no Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

