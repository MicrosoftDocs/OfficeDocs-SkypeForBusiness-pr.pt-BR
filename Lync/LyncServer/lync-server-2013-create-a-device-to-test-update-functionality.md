---
title: 'Lync Server 2013: criar um dispositivo para testar a funcionalidade de atualização'
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
ms.openlocfilehash: b197c4b42542310746568fe351f98c7d991509cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Criar um dispositivo para testar a funcionalidade de atualização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção. Você pode testar um dispositivo globalmente (em todo o ambiente do Lync Server) ou em um único site. Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série. Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Para adicionar um dispositivo de teste

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação à esquerda, clique em **clientes**e em **testar dispositivo**.

3.  Clique em **novo**e, em seguida, clique em **dispositivo de teste global** ou **dispositivo de teste de site**.

4.  Siga um destes procedimentos:
    
      - Se você clicou em **dispositivo de teste global**, pule para a próxima etapa.
    
      - Se você clicou em **site Test site**, selecione um site da lista de sites disponíveis e, em seguida, clique em **OK**.

5.  Em **novo dispositivo de teste**, digite um nome para o dispositivo no **nome do dispositivo**.

6.  Em **tipo de identificador**, clique em **endereço MAC** ou **número de série**.

7.  Na caixa **identificador exclusivo** , digite o endereço Mac ou o número de série do dispositivo.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Criando dispositivos de teste usando cmdlets do Windows PowerShell

Os dispositivos de teste podem ser criados usando o Windows PowerShell e o cmdlet New-CsTestDevice. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

Ao criar dispositivos de teste usando este cmdlet, você deve fazer duas coisas:

  - Especifique o MACAddress ou o SerialNumber como IdentifierType.

  - Inclua o escopo ao especificar a identidade do dispositivo. Para criar um novo dispositivo no escopo global, use a sintaxe semelhante a esta:
    
        -Identity "global/WindowsPhone"
    
    Para criar um dispositivo de teste na sintaxe de escopo do site, use a sintaxe semelhante a esta:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Para criar um dispositivo de teste usando o endereço MAC

  - Esse comando cria um dispositivo de teste no escopo global e usando o endereço MAC como Identificadortype:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Para criar um dispositivo de teste usando o número de série

  - Esse comando cria um novo dispositivo de teste no escopo do site (para o site Redmond) e usa o número de série como Identificadortype:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

