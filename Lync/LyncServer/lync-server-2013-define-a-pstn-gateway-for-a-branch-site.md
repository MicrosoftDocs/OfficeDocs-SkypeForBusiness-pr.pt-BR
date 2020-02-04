---
title: 'Lync Server 2013: Definir um gateway de PSTN para um site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definir um gateway de PSTN para um site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Execute este procedimento no site central, que contém pelo menos um pool de front-end ou um servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Antes de executar o procedimento, as seguintes condições devem estar em vigor: 
> <UL>
> <LI>
> <P>O software de&nbsp;comunicação do Lync Server 2013 deve ser configurado no site central.</P>
> <LI>
> <P>O servidor de mediação deve ser implantado no site central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Para definir um gateway PSTN

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server**e, em seguida, clique em **Construtor de topologia do Lync Server**.

2.  Na árvore de console, expanda o site central, expanda **sites de filiais**, expanda o nome do site de filial para o qual você deseja definir um gateway PSTN (rede telefônica pública comutada) para e, em seguida, expanda **componentes compartilhados**.

3.  Clique com o botão direito do mouse em **gateways PSTN**e clique em **novo gateway IP/PSTN**.

4.  Na caixa de diálogo **definir novo gateway IP/PSTN** , clique em **endereço IP ou FQDN do gateway**e digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do gateway que você está implantando no site da filial.

5.  Clique em **porta de escuta do gateway IP/PSTN**e aceite os valores padrão.

6.  Na lista **protocolo de transporte SIP** , clique no protocolo de transporte usado pelo gateway e, em seguida, clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos enfaticamente que você use um gateway PSTN compatível com TLS (Transport Layer Security).

    
    </div>

<div>


> [!TIP]  
> Use o cmdlet <STRONG>set-CsPstnGateway</STRONG> para modificar as propriedades de um gateway PSTN. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>na ajuda do Shell de gerenciamento do Lync Server.



</div>

**Próxima etapa** para resiliência no local da filial: [Configurando usuários para resiliência de site de ramificação no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Opções de implantação do gateway PSTN no Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

