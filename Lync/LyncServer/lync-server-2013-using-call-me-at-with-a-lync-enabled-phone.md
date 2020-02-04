---
title: 'Lync Server 2013: usando ligar para mim com um telefone compatível com o Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d4b117970cec1e40b4d18928f82bc0cf2831eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Usando ligar para mim com um telefone compatível com o Lync e o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-08-09_

O recurso ligar para mim no Lync fornece uma maneira para os usuários ingressarem na parte de áudio de uma conferência usando um telefone celular, "Land linha" ou outro dispositivo conectado à rede telefônica pública comutada (PSTN). Ao tentar ingressar em uma reunião usando o Lync, você normalmente será apresentado com a caixa de diálogo **ingressar no áudio da reunião** :

![Usar o Lync para ingressar na tela da janela de áudio da reunião](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Usar o Lync para ingressar na tela da janela de áudio da reunião")

Se você selecionar **ligar para mim**, pode escolher um número de telefone na lista suspensa. O Lync Server 2013 fará uma chamada telefônica para o número selecionado, e você poderá usar esse telefone para participar da parte de áudio da conferência.

A lista suspensa é preenchida pelos números de telefone (para celular, telefone residencial ou outro telefone) que você digitou na guia **telefones** na caixa de diálogo **Lync – opções** :

![Captura de tela de opções de configuração de telefones do Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de tela de opções de configuração de telefones do Lync")

Se você não inseriu nenhum número de telefone na guia **telefones** , você não terá nenhum número disponível na caixa suspensa. No entanto, você sempre pode clicar em **novo número** e fazer o Lync Server discar para qualquer número de telefone que desejar:

![Captura de tela do Lync ingressar na chamada de áudio da reunião na janela](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de tela do Lync ingressar na chamada de áudio da reunião na janela")

O recurso ligar para mim funciona muito bem para que você o use na maneira como foi destinado: ao fato de que o Lync Server chama um número de telefone PSTN. No entanto, você pode ter uma experiência menor do que a ideal se pedir ao Lync Server para chamá-lo em um ponto de extremidade compatível com o Lync (por exemplo, um telefone em uma sala de conferência). Veja a seguir o problema que você pode executar, bem como as duas maneiras de contornar o problema.

Para começar, veja o que acontece quando você fornece o recurso ligar para mim com o número de telefone de um telefone compatível com o Lync. Suponha que Ken Myer tente ingressar em uma reunião fazendo com que o Lync Server chame-o em 1-206-555-1219, um número de telefone habilitado para o Lync Server. Ken será conectado inicialmente à reunião, mas, após alguns segundos, o Lync exibirá a mensagem a **chamada não foi concluída ou foi encerrada**e Ken parecerá ter sido cancelada na reunião:

![Captura de tela da janela de conferência de chamadas do Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de tela da janela de conferência de chamadas do Lync")

Observe, porém, que há uma discrepância dentro da janela de conversa do Lync. Ken Myer é o único nome listado no título **participantes** . No entanto, se você olhar na barra de título da janela, verá que a conferência contém um total de 4 participantes.

Da mesma forma, se você olhar na janela de conversa de qualquer um dos outros participantes da conferência, você não verá Ken Myer listado em qualquer lugar:

![Captura de tela da janela lista de participantes do Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de tela da janela lista de participantes do Lync")

E ainda, ao mesmo tempo, Ken Myer poderá participar na parte de áudio da chamada usando seu telefone compatível com o Lync. Na verdade, o recurso ligar para mim funciona, mas a experiência do usuário é menos do que o ideal.

Há pelo menos duas maneiras de contornar esse problema. Se você já ingressou em uma conferência dessa maneira (como Ken Myer DID), normalmente é possível solucionar o problema ao envolver uma modalidade diferente. Por exemplo, se você enviar uma mensagem instantânea, a janela de conversa mostrará todos os participantes da conferência, incluindo você:

![Captura de tela de conversa e lista de participantes do Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de tela de conversa e lista de participantes do Lync")

Neste ponto, você poderá participar da reunião da maneira esperada.

Você também pode evitar esse problema alterando o modo como ingressa na reunião. Se você precisar fazer uma chamada no Lync Server para um telefone habilitado pelo Lync Server, você deve começar entrando na reunião sem uma conexão de áudio. Para fazer isso, selecione não ingressar no áudio quando aparecer a caixa de diálogo ingressar no áudio da reunião:

![A captura de tela da janela de áudio do Lync não ingressa na reunião](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "A captura de tela da janela de áudio do Lync não ingressa na reunião")

Depois de conectar-se à reunião com êxito, agora você pode "convidar" o telefone habilitado para Lync Server para ingressar na reunião também. Para fazer isso, coloque o mouse sobre o ícone pessoas e clique em **convidar mais pessoas**:

![Captura de tela de mais participantes do Lync INVITE](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de tela de mais participantes do Lync INVITE")

Isso exibirá a caixa de diálogo **Enviar uma mensagem instantânea** . Ignore o título da caixa de diálogo (você não está enviando uma mensagem instantânea) e digite o número de telefone do telefone compatível com o Lync:

![Enviar uma captura de tela de caixa de diálogo Enviar mensagem instantânea](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Enviar uma captura de tela de caixa de diálogo Enviar mensagem instantânea")

Depois que você clicar em **OK**, o Lync Server chamará o número inserido na caixa de diálogo. Quando a conexão for feita, você terá recursos de áudio completos por meio do telefone compatível com o Lync e poderá ver e interagir com a lista completa de conferências.

</div>

<span> </span>

</div>

</div>

</div>

