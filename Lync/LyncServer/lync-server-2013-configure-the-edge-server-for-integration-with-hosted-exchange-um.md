---
title: Configurar o servidor de borda para integração com o UM do Exchange hospedado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0779612ca4ebf33757f5d392d1619211aeb4a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>Configurar o servidor de borda para integração com o UM do Exchange hospedado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-01-23_

Para fornecer aos usuários do Lync Server 2013 com recursos de caixa postal na Unificação de mensagens (UM) do Exchange hospedada, você deve executar as seguintes tarefas de configuração no servidor de borda:

  - Configure o Servidor de Borda para federação.

  - Replique os dados do repositório de gerenciamento central para o servidor de borda e verifique a replicação.

  - Crie um provedor de hospedagem no Servidor de Borda.

Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> É necessário criar um registro DNS SRV para o serviço Exchange de hospedagem antes de você executar essas etapas. Para obter detalhes, consulte <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">criar um registro SRV de DNS para integração com a um do Exchange hospedado</A>.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>Para configurar o Servidor de Borda para federação

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsAccessEdgeConfiguration para configurar o servidor para federação. Por exemplo, execute:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    O exemplo anterior define os seguintes parâmetros:
    
      - **UseDnsSrvRouting** especifica se os Servidores de Borda dependerão dos registros DNS SRV ao enviar e receber solicitações de federação.
    
      - **AllowFederatedUsers** especifica se os usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em uma situação de divisão de domínios.
    
      - **EnablePartnerDiscovery** especifica se o Lync Server usará registros DNS para tentar descobrir domínios de parceiros não listados na lista de domínios permitidos do Active Directory. Se false, o Lync Server 2013 se federará apenas com domínios encontrados na lista de domínios permitidos. Esse parâmetro é obrigatório caso se esteja utilizando o roteamento de serviço de DNS. Na maioria das implantações, o valor é definido como falso para evitar abrir a federação a todos os parceiros.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>Para replicar os dados para o Servidor de Borda e verificar a replicação

  - Verifique se a replicação para o Servidor de Borda está completa. Para obter o procedimento, consulte [verificar a conectividade entre servidores internos e servidores de borda no Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>Para criar um provedor de hospedagem no Servidor de Borda

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsHostingProvider** para configurar o provedor de hospedagem. Por exemplo, execute:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    O exemplo anterior define os seguintes parâmetros:
    
      - **Identidade** especifica um identificador exclusivo de valor de cadeia de caracteres para o provedor de hospedagem que você está criando, neste exemplo, **Fabrikam.com**. Observe que o comando falhará se um provedor existente já tiver sido configurado com essa identidade.
    
      - **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. As mensagens não podem ser trocadas entre as duas organizações até que esse valor seja definido como **Verdadeiro**.
    
      - **EnabledSharedAddressSpace** indica se o provedor de hospedagem está sendo usado em um cenário de espaço de endereço SIP compartilhado (domínio dividido).
        
        <div>
        

        > [!NOTE]
        > Antes de definir <CODE>EnableSharedAddressSpace</CODE> como true, tente resolver o registro SRV de Federação internamente. Se este registro não puder ser resolvido internamente, você precisará criar os registros _sipfederationtls. _tcp. &lt;domain&gt; e _sip. _tls. &lt;domínio&gt; no DNS interno. Esses registros devem apontar para o endereço IP externo da interface de acesso do servidor de borda.

        
        </div>
    
      - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Lync Server 2013. Se estiver definido como **Falso**, o provedor hospedará outros tipos de conta, como contas do Microsoft Exchange.
    
      - **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem, neste exemplo, **proxyserver.fabrikam.com**. Esse valor não pode ser modificado. Se o provedor de hospedagem alterar o seu servidor proxy, será necessário excluir e recriar a entrada desse provedor.
    
      - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Lync Server 2013.
    
      - **VerficationLevel** indica o nível de verificação permitido para mensagens enviadas para e do provedor de hospedagem. Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se este nível não for especificado, a mensagem será rejeitada como sendo não-verificável.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Exporte sua topologia do Lync Server 2013 e copie-a para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Verificar a conectividade entre servidores internos e servidores de borda no Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

