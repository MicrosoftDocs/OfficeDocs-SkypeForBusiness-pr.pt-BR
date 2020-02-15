---
title: 'Lync Server 2013: executando preparação de domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960a3664bb7b629a9d66b375d072f826ed9e2738
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Executando a preparação do domínio para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-04-16_

Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar domínios. O cmdlet que prepara um domínio é **Enable-CsAdDomain**.

A preparação do domínio é a etapa final da preparação dos serviços de domínio do Active Directory para o Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Para usar a Instalação para preparar domínios

1.  Faça logon em qualquer servidor no domínio como membro do grupo Administradores de Domínio.

2.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.

3.  Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.

4.  Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.

5.  Na página **Preparar Domínio**, clique em **Avançar**.

6.  Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.

7.  Na coluna **ação** , expanda **domínio Prep**, procure um ** \<\> ** resultado de execução de êxito no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.

8.  Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in Sites e Serviços do Active Directory para o controlador de domínio raiz da floresta.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Para usar cmdlets para preparar o domínio

1.  Faça o logon em qualquer servidor do domínio como um membro do grupo Admins de Domínio.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.
    
    4.  Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  Sejam
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Por exemplo:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Se você não especificar o parâmetro de Domínio, o padrão é o domínio local.

5.  Verificar se a preparação de domínio teve êxito. Execute:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Por exemplo:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas. Se estiverem armazenadas no contêiner Sistema (o que é comum, quando as importações de atualização não tiveram a configuração global migrada para o contêiner Configuração), você definirá um controlador de domínio na raiz da sua floresta do Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é comum nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você definirá qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio&nbsp;no AD DS.

    
    </div>
    
    Se você não especificar o parâmetro **Domain** , o padrão será o domínio local.
    
    Este cmdlet retorna um valor de **LC\_DOMAINSETTINGS\_estado\_pronto** se a preparação do domínio tiver sido bem-sucedida.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

