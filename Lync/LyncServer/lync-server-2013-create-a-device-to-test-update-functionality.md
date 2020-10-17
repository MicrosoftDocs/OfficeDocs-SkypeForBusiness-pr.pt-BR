---
title: 'Lync Server 2013: criar um dispositivo para testar a funcionalidade de atualização'
description: 'Lync Server 2013: Crie um dispositivo para testar a funcionalidade de atualização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542167"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Criar um dispositivo para testar a funcionalidade de atualização no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o seu ambiente do Lync Server) ou em um único site. Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série. Quando você adiciona um dispositivo, ele aparece na lista na página **dispositivo de teste** do painel de controle do Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Para adicionar um dispositivo de teste

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Cliente** e em **Dispositivo de Teste**.

3.  Clique em **Novo** e em **Dispositivo de teste global** ou **Dispositivo de teste de site**.

4.  Siga um destes procedimentos:
    
      - Se você clicou em **Dispositivo de teste global**, vá para a próxima etapa.
    
      - Se você clicou em **Dispositivo de teste de site**, selecione um site na lista de sites disponíveis e clique em **OK**.

5.  Em **Novo Dispositivo de Teste**, digite um nome para o dispositivo em **Nome do dispositivo**.

6.  Em **Tipo de identificador**, clique em **Endereço MAC** ou **Número de série**.

7.  Na caixa **Identificador exclusivo**, digite o endereço MAC ou número de série do dispositivo.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Criando dispositivos de teste usando cmdlets do Windows PowerShell

Os dispositivos de teste podem ser criados usando o Windows PowerShell e o cmdlet New-CsTestDevice. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

Ao criar dispositivos de teste usando este cmdlet, você deve fazer duas coisas:

  - Especificar o MACAddress ou SerialNumber como o IdentifierType.

  - Incluir o escopo ao especificar a Identidade do dispositivo. Para criar um novo dispositivo no escopo global, use uma sintaxe semelhante a seguinte:
    
        -Identity "global/WindowsPhone"
    
    Para criar um dispositivo de teste no escopo do site, use uma sintaxe semelhante a esta:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Para criar um dispositivo de teste usando o endereço MAC

  - Este comando cria um dispositivo de teste no escopo global e usando o endereço MAC como o IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Para criar um dispositivo de teste usando o número de série

  - Este comando cria um novo dispositivo de teste no escopo local (o local Redmond) e usa o número de série como o IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

