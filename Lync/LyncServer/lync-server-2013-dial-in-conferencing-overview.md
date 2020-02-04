---
title: Visão geral da conferência discada do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Visão geral da conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Se a sua organização tiver usuários que precisem participar de conferências locais do Lync Server 2013 quando estiverem fora do escritório ou não tiverem acesso a um computador, você poderá implantar a conferência discada para que ela possa participar da conferência usando um telefone comutado público telefone de rede (PSTN).

A conferência discada é um recurso opcional que você pode configurar ao implantar a conferência do Lync Server 2013. Embora a conferência discada use alguns dos mesmos componentes do Lync Server 2013 que o Enterprise Voice usa, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice.

<div>


> [!NOTE]  
> Se você implantar a conferência discada, será necessário implantá-la em cada pool onde implantar a conferência do Lync Server 2013. Você não precisa atribuir números de acesso em cada pool, mas você deve implantar o recurso de discagem em cada pool. Esse requisito dá suporte ao recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Lync Server 2013 em um pool diferente.



</div>

As conferências devem estar habilitadas para acesso de discagem na política de reunião. Por padrão, as conferências que estão ativadas para o acesso de discagem incluem as seguintes informações na solicitação de conferência:

  - Uma ID de conferência numérica que identifica a conferência.

  - Um ou mais números de acesso PSTN.

  - Um link para uma página de configurações de conferência discada, que contém uma lista completa de números de acesso com seus idiomas associados; um local para criar, redefinir ou desbloquear números de identificação pessoal (PINs); e outras informações, como controles DTMF (Multifrequency Multi-Frequency) de Tom duplo.

A conferência discada é compatível com usuários corporativos e anônimos. Os usuários empresariais têm as credenciais dos serviços de domínio Active Directory e do Lync Server 2013 em sua organização. Os usuários anônimos não têm credenciais da empresa dentro de sua organização. No contexto de conferência de discagem, um usuário em uma organização de um parceiro federado que usa o PSTN para se conectar a uma conferência é tratado como usuário anônimo. Diferentemente de em outros contextos, para a conferência discagem os usuários federados não são autenticados.

Os usuários corporativos ou líderes de conferência que ingressam em uma conferência estão habilitados para o acesso de discagem discam um dos números de acesso de conferência e, em seguida, são solicitados a inserir o ID de conferência. Se um líder ainda não ingressou na reunião, os usuários podem digitar a sua extensão de comunicações unificadas (UC) (ou número de telefone completo) e PIN ou aguardar para ser admitidos pelo líder. Os organizadores de reuniões podem ingressar na reunião como líderes apenas digitando o seu PIN. O Servidor de Front-End usa a combinação do número completo ou extensão de telefone e o PIN, para mapear exclusivamente os usuários corporativos para as credenciais do Active Directory. Como resultado, os usuários corporativos são autenticados e identificados pelo nome da conferência. Os usuários corporativos também podem assumir um papel de conferência predefinido pelo organizador.

<div>


> [!NOTE]  
> Os usuários da empresa que discam de um telefone IP do Office ou do Lync Server 2013 ou Lync 2010 Attendant não são solicitados para seu número de telefone porque já estão autenticados.



</div>

Os usuários anônimos que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência e, em seguida, são solicitado a inserir o ID de conferência. Os usuários anônimos não autenticados também têm que registrar o seu nome. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.

<div>


> [!NOTE]  
> Os usuários corporativos que optam por não inserir o número de telefone e o PIN não são autenticados. Eles serão solicitados a registrar seu nome e são tratados como usuários anônimos na conferência.



</div>

No momento do cronograma, o organizador da reunião pode optar por restringir o acesso à reunião fazendo com que a reunião seja fechada ou bloqueada. Nesse caso, os usuários de discagem devem ser autenticados. Se os usuários de discagem falharem ou optarem por não autenticar, eles serão transferidos para o lobby. Elas esperam no lobby até que um líder a aceite ou rejeite, ou que o tempo limite e seja desconectado. Os usuários de discagem ouvirão música se estiverem aguardando para serem admitidos na conferência. Depois de serem admitidos em uma conferência, os usuários de discagem podem participar do áudio da conferência e executar comandos de multifrequência de tom dual (DTMF) com o teclado do telefone. Líderes de discagem podem executar comandos DTMF para ativar ou desativar a capacidade dos participantes de desativar Mudo, bloquear ou desbloquear a conferência, admitir pessoas do lobby e ativar ou desativar os anúncios de entrada/saída. Os líderes também podem usar um comando DTMF para admitir todos do lobby, o que altera as permissões de reunião para permitir qualquer um que participe depois. Todos os participantes de discagem podem executar comandos DTMF par ouvir a Ajuda, ouvir os participantes da conferência e ativar Mudo para si próprios.

Participantes de discagem (ou seja, se eles discarem da PSTN), ouvirão comunicados pessoais durante a conferência, como se estivessem com mudo ativado ou mudo, se a reunião está sendo gravada ou se alguém está aguardando no lobby.

<div>


> [!NOTE]  
> Os participantes que ingressam na conferência clicando em um link, em vez de discando, não ouvem os comunicados pessoais.



</div>

</div>

<span> </span>

</div>

</div>

</div>

