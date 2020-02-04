---
title: 'Lync Server 2013: Configurando servidores de proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbc6e0aee918d08f47c6df88f91493cd62ae6a3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configurando servidores de proxy reverso para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-08_

Para implantações do Microsoft Lync Server 2013 Edge Server, um proxy reverso HTTPS na rede de perímetro é necessário para clientes externos acessarem os serviços da Web do Lync Server 2013 (chamados de *componentes da Web* no Office Communications Server) no diretor e no pool de casa do usuário. Alguns dos recursos que exigem acesso externo por meio de um proxy reverso incluem o seguinte:

  - Permitir que usuários externos Baixem o conteúdo da reunião para suas reuniões.

  - Permitir que usuários externos expandam grupos de distribuição.

  - Permitir que usuários remotos baixem arquivos do serviço de catálogo de endereços.

  - Acessando o cliente Lync Web App.

  - Acessando a página de configurações de conferência discada.

  - Habilitando dispositivos externos para se conectar ao serviço Web de atualização de dispositivos e obter atualizações.

  - Permitir que aplicativos móveis descubram e usem automaticamente as URLs de mobilidade (MCX) da Internet.

  - Habilitando o cliente do Lync 2013, o aplicativo Lync da Windows Store e o cliente móvel do Lync 2013 para localizar as URLs de descoberta do Lync (descoberta automática) e usar a API da Web de comunicação unificada (UCWA).

Recomendamos que você configure seu proxy reverso HTTP para publicar todos os serviços Web em todos os pools. Publishing https://ExternalFQDN/\* publica todos os diretórios virtuais do IIS para um pool. Você precisa de uma regra de publicação para cada servidor Standard Edition, o pool de front-end ou o diretor ou o pool do diretor da sua organização.

Além disso, você precisa publicar as URLs simples. Se a organização tiver um director ou um pool de directors, o proxy reverso HTTP escutará solicitações HTTP/HTTPS para URLs simples e os proxies para o diretório virtual de serviços Web externos no director ou no pool do diretor. Se você não implantou um director, será necessário designar um pool para manipular as solicitações para as URLs simples. (Se esse não for o pool inicial do usuário, ele será redirecionado para os serviços Web no pool primário do usuário). As URLs simples podem ser manipuladas por uma regra de publicação da Web dedicada ou você pode adicioná-la aos nomes públicos da regra de publicação na Web do diretor. Você também precisa publicar a URL do serviço de descoberta automática externa.

Você pode usar o Microsoft Forefront Threat Management Gateway 2010, o Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou o Internet Information Server 7,0, 7,5 ou 8,0 com o roteamento de solicitação de aplicativo (IIS ARR) como um proxy reverso. As etapas detalhadas desta seção descrevem como configurar o Forefront Threat Management Gateway 2010, e as etapas para configurar o ISA Server 2006 são quase idênticas. Também é oferecida uma orientação para o IIS ARR. Se você estiver usando um proxy reverso diferente, consulte a documentação desse produto e mapeie os requisitos definidos aqui para os recursos associados em outros proxies reverso.

<div>


> [!IMPORTANT]  
> Roteamento de solicitação de aplicativo do Internet Information Server (IIS ARR) é uma opção totalmente testada e com suporte para implementar um proxy reverso para o Lync Server 2010 e o Lync Server 2013. Em novembro de 2012, a Microsoft parou as vendas de licenças do ForeFront Threat Management Gateway 2010 ou da TMG. A TMG ainda é um produto totalmente compatível e ainda está disponível para venda em aparelhos vendidos por terceiros. Além disso, vários balanceadores de carga de hardware e firewalls de terceiros fornecem suporte de proxy reverso. Para os balanceadores de carga de hardware e os firewalls que fornecem recursos de proxy reverso, consulte o fornecedor para obter instruções específicas sobre como configurar o produto para fornecer suporte de proxy reverso ao Lync Server. Você também pode ver terceiros que enviaram documentação de seus produtos para a Microsoft. O suporte é fornecido por terceiros para sua solução. Para ver terceiros ativos no fornecimento de soluções, consulte <A href="http://go.microsoft.com/fwlink/?linkid=268730">infraestrutura qualificada para Microsoft Lync</A>.



</div>

Os tópicos e procedimentos a seguir usam o Forefront Threat Management Gateway 2010 e o IIS ARR como base para os procedimentos de implantação e configuração.

  - [Configurar FQDNs da web farm para Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurar adaptadores de rede no Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurar regras de publicação na Web para um único pool interno no Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Verificar ou configurar autenticação e certificação nos diretórios virtuais de IIS no Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Criar registros de DNS para servidores de proxy reverso no Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Verificar acesso por meio de seu proxy reverso no Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Antes de começar

Para implantar com êxito o 2010 do Forefront Threat Management Gateway como seu proxy reverso, você precisa configurar e configurar um servidor, usando os pré-requisitos e requisitos de hardware definidos na documentação do Forefront Threat Management Gateway 2010. Consulte o conjunto de tópicos a seguir para configurar corretamente o hardware e instalar o 2010 do Forefront Threat Management Gateway no servidor antes de prosseguir.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recomendações de hardware do Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Para implantar com êxito o ARR do IIS como seu proxy reverso, examine os tópicos a seguir para configurar o hardware e o software de pré-requisito.

  - <span></span>  
    Para instalar o IIS no Windows Server 2008 ou no Windows Server 2008 R2, confira [instalando o IIS 7 no Windows server 2008 ou Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Para instalar o IIS no Windows Server 2012, confira [instalando o IIS 8 no Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Para instalar o IIS no Windows Server 2012 R2, confira [instalando o iis 8,5 no Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Para baixar a extensão de roteamento de solicitação do aplicativo para o IIS, siga as instruções em [solicitação do aplicativo roteamento v 2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Para instalar o ARR, para as instruções no [artigo instalar o roteamento de solicitação de aplicativo versão 2](http://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > As instruções publicadas atualmente são para o ARR 2,0. Para a instalação da extensão, não há diferença entre as duas versões.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

