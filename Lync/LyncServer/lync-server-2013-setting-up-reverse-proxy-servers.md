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
ms.openlocfilehash: 9f4ff853e3f31804e4bca55bd6a4576e25702b6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configurando servidores de proxy reverso para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-08_

Para implantações do servidor de borda do Microsoft Lync Server 2013, um proxy reverso HTTPS na rede de perímetro é necessário para que clientes externos acessem os serviços Web do Lync Server 2013 (chamados de *componentes da Web* no Office Communications Server) no diretor e o pool de casa do usuário. Veja abaixo alguns dos recursos que exigem acesso externo por meio de proxy reverso:

  - Permitir que usuários externos baixem o conteúdo de reunião para suas reuniões.

  - Permitir que usuários externos expandam grupos de distribuição.

  - Permitir que usuários remotos baixem arquivos do serviço de Catálogo de Endereços.

  - Acessar o cliente Lync Web App.

  - Acessar a página da web de Configurações de Conferência Discada.

  - Permitir que dispositivos externos se conectem ao serviço web de Atualização de Dispositivo e obtenham atualizações.

  - Permitir que aplicativos móveis descubram e usem automaticamente as URLs de mobilidade (MCX) a partir da Internet.

  - Habilitando o cliente do Lync 2013, o aplicativo Lync Windows Store e o cliente móvel do Lync 2013 para localizar as URLs de descoberta do Lync (descoberta automática) e usar o UCWA (Unified Communications Web API).

Recomendamos que configure seu proxy reverso HTTP para publicar todos os Serviços Web em todos os pools. Publishing https://ExternalFQDN/\* publica todos os diretórios virtuais do IIS para um pool. Você precisa de uma regra de publicação para cada servidor Standard Edition, pool de Front-Ends ou Diretores, ou Diretores em sua organização.

Além disso, você precisa publicar as URLs simples. Caso a organização possua um Diretor ou pool de Diretores, o proxy reverso HTTP escuta por solicitações HTTP/HTTPS às URLs simples e as encaminha via proxy ao diretório virtual de Serviços Web externos no Diretor  ou pool de Diretores. Caso você não tenha implantado um diretor, você precisará designar um pool para manipular as solicitações às URLs simples. (Caso este não seja o pool inicial do usuário, ele irá redirecioná-los para o Serviços Web no pool inicial do usuário). As URLs simples podem ser manipuladas por uma regra de publicação de web dedicada ou você pode adicioná-la aos nomes públicos da regra de publicação de web para o Diretor. Você também precisa publicar a URL externa do serviço de descoberta automática.

Você pode usar o Microsoft Forefront Threat Management Gateway 2010, o Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou o Internet Information Server 7,0, 7,5 ou 8,0 com o serviço de roteamento de solicitação de aplicativo (IIS ARR) como um proxy reverso. As etapas detalhadas nesta seção descrevem como configurar o Forefront Threat Management Gateway (TMG) 2010 e as etapas para configurar o ISA Server 2006 são quase idênticas. As orientações também são fornecidas para o IIS ARR. Se você estiver usando outro proxy reverso, consulte a documentação do produto e mapeie os requisitos definidos aqui para os recursos associados em outros proxies reversos.

<div>


> [!IMPORTANT]  
> Serviço de roteamento de solicitação de aplicativo do Internet Information Server (IIS ARR) é uma opção totalmente testada e com suporte para implementar um proxy reverso para Lync Server 2010 e Lync Server 2013. Em novembro de 2012, a Microsoft deixou vendas de licenças do ForeFront Threat Management Gateway 2010 ou TMG. A TMG ainda é um produto com suporte completo e ainda está disponível para venda nos dispositivos vendidos por terceiros. Além disso, vários balanceadores de carga de hardware e firewalls de terceiros oferecem suporte de proxy reverso. Para balanceadores de carga de hardware e firewalls que oferecem recursos de proxy reverso, consulte seu fornecedor para obter instruções específicas sobre como configurar o produto para fornecer suporte de proxy reverso para o Lync Server. Você também pode exibir as terceiros que enviaram a documentação do produto para a Microsoft. O suporte é fornecido por terceiros para sua solução. Para ver terceiros que estão ativos no fornecimento de soluções, consulte <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure Qualified for Microsoft Lync</A>.



</div>

Os seguintes tópicos e procedimentos usam o Forefront Threat Management Gateway 2010 e o IIS ARR como base para os procedimentos de implantação e configuração.

  - [Configurar FQDNs do Web farm para o Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurar adaptadores de rede no Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurar regras de publicação na Web para um único pool interno no Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Verificar ou configurar a autenticação e certificação nos diretórios virtuais do IIS no Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Criar registros DNS para servidores de proxy reverso no Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Verificar o acesso por meio de seu proxy reverso no Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Antes de começar

Para implantar com êxito o Forefront Threat Management Gateway 2010 como seu proxy reverso, é necessário configurar um servidor, usando os pré-requisitos e requisitos de hardware definidos na documentação do Forefront Threat Management Gateway 2010. Consulte o tópico a seguir para configurar corretamente o hardware e para instalar o Forefront Threat Management Gateway 2010 no servidor antes de continuar.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recomendações de hardware do Forefront TMG 2010](https://go.microsoft.com/fwlink/?linkid=291293)

Para implantar o IIS ARR como seu proxy reverso, revise os tópicos a seguir para configurar o hardware e o software de pré-requisito.

  - <span></span>  
    Para instalar o IIS no Windows Server 2008 ou no Windows Server 2008 R2, consulte [instalando o IIS 7 no Windows server 2008 ou Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Para instalar o IIS no Windows Server 2012, consulte [instalando o IIS 8 no Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Para instalar o IIS no Windows Server 2012 R2, consulte [instalando o iis 8,5 no Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Para baixar a extensão de roteamento de solicitação de aplicativo para o IIS, siga as instruções em [download de roteamento de solicitação de aplicativo v 2.5](https://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Para instalar o ARR, para as instruções em [instalar o encaminhamento de solicitação de aplicativo versão 2](https://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > As instruções atualmente postadas são para o ARR 2,0. Para a instalação da extensão, não há diferença entre as duas versões.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

