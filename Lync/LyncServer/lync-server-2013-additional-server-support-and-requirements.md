---
title: 'Lync Server 2013: suporte e requisitos adicionais do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b83f900a5d6ccca9932b68e012d5c0dbbd6d23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Suporte e requisitos adicionais do servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-09_

Além do suporte de software descrito nas outras seções desta documentação de suporte, o Lync Server 2013 tem as seguintes limitações de suporte:

  - O Lync Server 2013 suporta o DNS (sistema de nomes de domínio) e o balanceamento de carga de hardware para funções de servidor específicas. Ele também suporta o balanceamento de carga de aplicativo para Servidores de Mediação, onde for aplicável. Para obter detalhes sobre quando usar cada um, consulte a documentação de Planejamento.

  - O Lync Server 2013 usa o DLX (Distribution List Expansion Protocol) para expandir as listas de distribuição. Esse protocolo também especifica o método de serviço Web que é usado para obter a participação de uma lista de distribuição. O Microsoft Exchange Server oferece suporte a grupos dinâmicos que não têm Membros atribuídos estaticamente a eles. Em vez disso, eles armazenam consultas que são avaliadas quando o grupo é expandido. O DLX não oferece suporte a listas de distribuição dinâmicas. Essa limitação de DLX se aplica a todas as versões do Lync Server.

  - O Assistente para Habilitar Usuário não oferece suporte à conversão automática de caracteres do inglês para um URI compatível com SIP; portanto, você deve modificar manualmente o endereço SIP.

  - Para servidores que executam software antivírus, consulte [exclusões de verificação antivírus para o Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) para exclusões de vírus sugeridas e outras recomendações relacionadas à segurança.

  - Se você usa o IPsec, recomendamos desativar o IPsec nos intervalos de porta usados para o tráfego de áudio e vídeo. Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.

  - Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente. Para obter detalhes sobre como implementar a QoS, consulte [Managing Quality of Service (QoS) no Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) na documentação operações.

  - O uso do firewall do sistema operacional é suportado. O Lync Server 2013 gerencia as exceções de firewall para o Firewall do sistema operacional, exceto para o software de banco de dados do Microsoft SQL Server. Para obter detalhes sobre os requisitos de firewall SQL Server, consulte a documentação do SQL Server.

  - As interfaces externas usadas para implementar o suporte ao acesso de usuário externo devem estar em uma sub-rede separada, *não* na mesma rede que as interfaces internas.

  - O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk. Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.

  - Com o lançamento das atualizações cumulativas do Lync Server 2013:2013 de julho, o Lync Server 2013 agora oferece suporte à autenticação de dois fatores. Para obter mais informações, consulte [autenticação de dois fatores no Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - A maioria dos servidores internos requer um tipo de certificado definido como **autenticação aberta** (OAuth). Você precisa solicitar e atribuir um certificado OAuth durante a fase **solicitar, instalar e atribuir certificados** do assistente de implantação do Lync Server. O tamanho mínimo de uma chave de certificado OAuth é de 1024 bits. Um aviso pode ser exibido se você solicitar um certificado com um tamanho de chave inferior a 2048 bits de comprimento. Para evitar possíveis problemas no caso de um comprimento de chave de 2048 ser aplicado em vez de avisado, é altamente recomendável usar sempre um comprimento de chave de 2048 para certificados OAuth.

  - O Lync Server 2013 e o Microsoft Exchange Server 2010 Service Pack 1 (SP1) operam com suporte para algoritmos de 140-2 padrão FIPS (Federal Information Processing Standard) se os sistemas operacionais Windows Server 2008 R2 estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia de sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor executando o Lync Server 2013 para dar suporte a ele. Para obter detalhes sobre algoritmos compatíveis com FIPS e como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento da Microsoft, "criptografia de sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e assinatura no Windows [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)XP e em versões posteriores do Windows em. Para obter detalhes sobre o suporte a FIPS 140-2 e limitações no Exchange 2010, consulte "Exchange 2010 SP1 and Support for FIPS compliant [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)algoritmos" em.

O Lync Server 2013 requer a instalação de outro software em componentes específicos antes ou durante a implantação. Isso inclui software disponível com o sistema operacional, software baixável e software que é instalado automaticamente durante a instalação do Lync Server 2013. A seguinte lista cita os softwares adicionais que podem ser necessários:

  - Windows Update

  - Windows Identity Foundation

  - Estrutura do Microsoft .NET 4,5

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > O Microsoft Visual C++ 2012 Redistributable é instalado automaticamente quando você instala o Lync Server 2013. Você não deve instalar e usar qualquer outra versão.

    
    </div>

  - URL Rewrite Module versão 2.0 Redistributable

  - Tempo de Execução do Windows Media Format

  - Windows PowerShell versão 3,0

  - Plug-in do navegador Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou a versão mais recente do Painel de Controle do Lync Server)

  - Ferramentas de serviços de domínio do Active Directory

Alguns desses requisitos de software se aplicam somente a funções específicas de servidor ou componentes. Para obter detalhes sobre esses requisitos de software, consulte [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

