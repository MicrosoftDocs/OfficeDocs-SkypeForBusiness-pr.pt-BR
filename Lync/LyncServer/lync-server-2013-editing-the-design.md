---
title: 'Lync Server 2013: Editando o design'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Editando o design no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.

A ferramenta de planejamento exibe a topologia de site para o site selecionado. Na parte inferior da página do site, existem quatro guias:

![Topologia do site da ferramenta de planejamento](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia do site da ferramenta de planejamento")

  - Topologia do site - A página exibida atualmente com uma visão geral visual da topologia, conforme recomendado.

  - Diagrama de rede Edge – a página de diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento. O diagrama exibe a configuração de rede para uma topologia do Lync Server 2013 recomendada, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga de DNS (sistema de nome de domínio) e de hardware.

  - Relatório de administração de borda - O Relatório de administração de borda contém um total de quatro relatórios:
    
    ![Página de relatório de administração de borda](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página de relatório de administração de borda")  
    
      - Relatório resumido - Um relatório geral de configurações para a configuração da Rede de borda. Se você editar os valores na página **Diagrama da rede de borda ** para a topologia TCP/IP e os valores do FQDN que irão ser usados na implantação atual, tais endereços e nomes serão representados aqui. De outro modo, o texto padrão aparecerá.
    
      - Relatório de certificado - O relatório de certificado listará o nome da entidade ou os nomes alternativos da entidade dos certificados que são exigidos para a topologia.
    
      - Relatório de firewall - O relatório de firewall lista as informações necessárias para configurar os firewalls de perímetro na infraestrutura. Isso inclui os endereços IP (seja de valores padrão ou editados), função do servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e notas relevantes.
    
      - Relatório de DNS - O relatório de DNS lista as informações relevantes para as entradas de DNS que você deve criar. Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.

  - Resumo do site - O resumo do site apresenta uma visão geral das seleções que foram feitas ao responder às perguntas da entrevista inicial ou ao incluir valores em **Criar Sites**. A informação de capacidade também é apresentada.
    
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

