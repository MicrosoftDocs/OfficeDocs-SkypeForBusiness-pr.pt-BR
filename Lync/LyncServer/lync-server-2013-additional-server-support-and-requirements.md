---
title: 'Lync Server 2013: Suporte adicional e requisitos de servidor'
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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Suporte adicional e requisitos de servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-09_

Além do suporte de software descrito nas outras seções desta documentação de suporte, o Lync Server 2013 tem as seguintes limitações de suporte:

  - O Lync Server 2013 suporta o sistema de nomes de domínio (DNS) e o balanceamento de carga de hardware para funções específicas do servidor. Ele também aceita o balanceamento de carga do aplicativo para servidores de mediação, quando adequado. Para obter detalhes sobre quando usar cada um, consulte a documentação de planejamento.

  - O Lync Server 2013 usa o protocolo de expansão de lista de distribuição (DLX) para expandir as listas de distribuição. Esse protocolo também especifica o método de serviço Web que é usado para obter a associação de uma lista de distribuição. O Microsoft Exchange Server oferece suporte a grupos dinâmicos que não têm Membros atribuídos estaticamente a eles. Em vez disso, elas armazenam consultas que são avaliadas quando o grupo é expandido. DLX não dá suporte a listas de distribuição dinâmicas. Esta limitação DLX se aplica a todas as versões do Lync Server.

  - O assistente habilitar usuário não dá suporte à conversão automática de caracteres que não estão em inglês em um URI compatível com SIP, portanto, você deve modificar o endereço SIP manualmente.

  - Para servidores que executam o software antivírus, consulte [exclusões de verificação de antivírus para o Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) para obter exclusões de vírus sugeridas e outras recomendações relacionadas à segurança.

  - Se você usa IPsec, recomendamos desabilitar o IPsec sobre os intervalos de porta usados para tráfego de áudio e vídeo. Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.

  - Se a sua organização usa uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia é projetado para funcionar com essa infraestrutura existente. Para obter detalhes sobre a implementação de QoS, consulte [Gerenciando a qualidade do serviço (QoS) no Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) na documentação de operações.

  - Há suporte para o uso do firewall do sistema operacional. O Lync Server 2013 gerencia as exceções de firewall para o Firewall do sistema operacional, exceto para o software de banco de dados do Microsoft SQL Server. Para obter detalhes sobre os requisitos de firewall do SQL Server, consulte a documentação do SQL Server.

  - As interfaces externas usadas para implementar o suporte para acesso de usuário externo devem estar em uma sub-rede separada, e *não* na mesma rede que as interfaces internas.

  - O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.

  - Com o lançamento das atualizações cumulativas do Lync Server 2013:2013 de julho, o Lync Server 2013 agora oferece suporte à autenticação de dois fatores. Para obter mais informações, consulte [autenticação de dois fatores no Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).

  - A maioria dos servidores internos exige um tipo de certificado definido como **autenticação aberta** (OAuth). Você precisa solicitar e atribuir um certificado OAuth durante a fase **solicitar, instalar e atribuir certificados** do assistente de implantação do Lync Server. O tamanho mínimo de uma chave de certificado OAuth é de 1024 bits. Um aviso pode ser exibido se você solicitar um certificado com um comprimento de chave inferior a 2048 bits de comprimento. Para evitar possíveis problemas no caso de um comprimento de chave do 2048 ser aplicado em vez de advertido, é altamente recomendável usar sempre um comprimento de chave de 2048 para certificados OAuth.

  - O Lync Server 2013 e o Microsoft Exchange Server 2010 Service Pack 1 (SP1) operam com suporte para algoritmos de 140-2 padrão FIPS (Federal Information Processing Standard) se os sistemas operacionais Windows Server 2008 R2 estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia do sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor que está executando o Lync Server 2013 para dar suporte a ele. Para obter detalhes sobre algoritmos compatíveis com FIPS e sobre como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento Microsoft, "criptografia do sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e autenticação de segurança [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)no Windows XP e em versões posteriores do Windows em. Para obter detalhes sobre o suporte e as limitações do FIPS 140-2 no Exchange 2010, consulte "Exchange 2010 SP1 e suporte para algoritmos compatíveis com FIPS" em [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).

O Lync Server 2013 requer a instalação de outro software em componentes específicos antes ou durante a implantação. Isso inclui software que está disponível com o sistema operacional, software para download e software que é instalado automaticamente durante a instalação do Lync Server 2013. Veja a seguir uma lista de softwares adicionais que podem ser necessários:

  - Windows Update

  - Windows Identity Foundation

  - Estrutura do Microsoft .NET 4,5

  - Microsoft Visual C++ 2012 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 2012 Redistributable é instalado automaticamente quando você instala o Lync Server 2013. Você não deve instalar e usar nenhuma outra versão.

    
    </div>

  - Módulo de regravação de URL versão 2,0 redistribuível

  - Tempo de Execução do Windows Media Format

  - Windows PowerShell versão 3,0

  - Plug-in do navegador Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou a versão mais recente para o painel de controle do Lync Server)

  - Ferramentas de serviços de domínio Active Directory

Alguns desses requisitos de software só se aplicam a funções ou componentes específicos do servidor. Para obter detalhes sobre esses requisitos de software, consulte [requisitos de software adicionais para o Lync Server 2013](lync-server-2013-additional-software-requirements.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

