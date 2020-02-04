---
title: 'Lync Server 2013: Executando preparação de domínio'
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
ms.openlocfilehash: 408dea780b4136f86ffed30d199d1d0ee63d6821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Executando preparação de domínio para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-04-16_

Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar domínios. O cmdlet que prepara um domínio é **Enable-CsAdDomain**.

Preparação do domínio é a etapa final na preparação dos serviços de domínio Active Directory para o Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Para usar a configuração para preparar domínios

1.  Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.

2.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.

3.  Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.

4.  Na **Etapa 5: preparar o domínio atual**, clique em **Executar**.

5.  Na página **preparar domínio** , clique em **Avançar**.

6.  Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.

7.  Na coluna **ação** , expanda o **domínio Prep**, procure um ** \<resultado\> ** de execução de sucesso no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.

8.  Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in sites e serviços do Active Directory do controlador de domínio raiz da floresta.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Usar cmdlets para preparar o domínio

1.  Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.

2.  Instale os componentes principais do Lync Server da seguinte maneira:
    
    1.  Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.
    
    2.  Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.
    
    3.  A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server. Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.
    
    4.  Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**. O instalador instala os componentes principais do Lync Server 2013.

3.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

4.  Execute:
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Por exemplo:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Se você não especificar o parâmetro Domain, o padrão será o domínio local.

5.  Verifique se a preparação do domínio foi bem-sucedida. Execute:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Por exemplo:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais são armazenadas. Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram as configurações globais migradas para o contêiner de configuração), defina um controlador de domínio na raiz da sua floresta do Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet pressupõe que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio no&nbsp;AD DS.

    
    </div>
    
    Se você não especificar o parâmetro **Domain** , o padrão será o domínio local.
    
    Esse cmdlet retorna um valor do **estado\_\_\_DOMAINSETTINGS da LC pronto** se a preparação do domínio tiver sido bem-sucedida.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Preparando domínios para Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

