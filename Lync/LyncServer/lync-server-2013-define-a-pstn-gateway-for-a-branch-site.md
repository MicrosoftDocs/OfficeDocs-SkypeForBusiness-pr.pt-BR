---
title: 'Lync Server 2013: definir um gateway PSTN para um site de filial'
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
ms.openlocfilehash: a8a47e395e74dae1eb6ec454e63fb343dcea7872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Definir um gateway PSTN para um site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Execute este procedimento no site central, que contém pelo menos um pool de front-ends ou servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Antes de executar o procedimento, as seguintes condições devem estar presentes: 
> <UL>
> <LI>
> <P>O software de&nbsp;comunicações do Lync Server 2013 deve ser configurado no site central.</P>
> <LI>
> <P>O servidor de mediação deve ser implantado no site central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Para definir um gateway PSTN

1.  Clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server** e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, expanda o site central, expanda **Sites de filial do escritório** e expanda o nome do site da filial para o qual você deseja definir um gateway PSTN (rede telefônica pública comutada) e expanda **Componentes compartilhados**.

3.  Clique com o botão direito do mouse em **Gateways PSTN** e clique em **Novo gateway IP/PSTN**.

4.  Na caixa de diálogo **Definir novo gateway IP/PSTN**, clique em **FQDN ou endereço IP do gateway** e digite o FQDN ou endereço IP do gateway que você vai implantar na filial.

5.  Clique em **Porta de escuta do Gateway IP/PSTN** e aceite os valores padrão.

6.  Na lista **Protocolo de Transporte SIP**, clique no protocolo de transporte que o gateway usa e em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos que você use um gateway PSTN que oferece suporte à segurança de camada de transporte (TLS).

    
    </div>

<div>


> [!TIP]  
> Use o cmdlet <STRONG>Set-CsPstnGateway</STRONG> para modificar as propriedades de um gateway PSTN. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>, na ajuda do Shell de gerenciamento do Lync Server.



</div>

**Próxima etapa** para resiliência de site de filial: [Configurando usuários para resiliência de site de filial no Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Opções de implantação de gateway PSTN no Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

