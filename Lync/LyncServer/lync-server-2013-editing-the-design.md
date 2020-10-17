---
title: 'Lync Server 2013: editando o design'
description: 'Lync Server 2013: editando o design.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20462c1c1813551159e8eeb3b255bd9069e3cce1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570617"
---
# <a name="editing-the-design-in-lync-server-2013"></a>Editando o design no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Após concluir as perguntas de entrevista inicial, você pode editar o FQDN (nome de domínio totalmente qualificado) e os endereços IP para o site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.

A ferramenta de planejamento exibe a topologia do site para o site selecionado. Na parte inferior da página do site, existem quatro guias:

![Topologia do site da ferramenta de planejamento](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia do site da ferramenta de planejamento")

  - Topologia do site – A página exibida atualmente com uma visão geral visual da topologia, conforme recomendado.

  - Diagrama de rede de borda – a página do diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento. O diagrama exibe a configuração de rede para uma topologia recomendada do Lync Server 2013, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga do DNS (sistema de nomes de domínio) e hardware.

  - Relatório de administração de borda – O Relatório de administração de borda contém um total de quatro relatórios:
    
    ![Página de relatório de administração de borda](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página de relatório de administração de borda")  
    
      - Relatório resumido – Um relatório geral de configurações para a Rede de borda. Se você editar os valores na página do **diagrama de rede de borda** para os valores de topologia TCP/IP e FQDN do que serão usados na implantação real, esses endereços e nomes serão representados aqui. Caso contrário, o texto padrão será exibido.
    
      - Relatório de certificado – O relatório de certificado listará o nome da entidade ou os nomes alternativos da entidade dos certificados que são exigidos para a topologia.
    
      - Relatório de firewall – O relatório de firewall lista as informações necessárias para configurar os firewalls de perímetro na infraestrutura. Isso inclui os endereços IP (os valores padrão ou editados), função de servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e anotações relevantes.
    
      - Relatório DNS – o relatório DNS lista informações relevantes para as entradas de DNS que devem ser criadas. Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.

  - Resumo do site – o resumo do site apresenta uma visão geral das seleções que você fez respondendo às perguntas de entrevista inicial ou preenchendo os valores em **sites de design**. As informações sobre capacidade também são apresentadas.
    
    <div>
    

    > [!NOTE]  
    > As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.

    
    </div>

<div>

## <a name="see-also"></a>Confira também


[Editando o diagrama de configuração de rede no Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

