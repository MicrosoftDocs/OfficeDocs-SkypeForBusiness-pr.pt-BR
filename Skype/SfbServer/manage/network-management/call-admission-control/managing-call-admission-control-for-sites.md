---
title: Gerenciando o controle de admissão de chamada para sites
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sites de rede são os escritórios ou locais dentro de cada região de rede de chamam (CAC) do controle de admissão, E9-1-1 e implantações de bypass de mídia.
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895416"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gerenciar o controle de admissão de chamadas para sites no Skype for Business Server

Sites de rede são os escritórios ou locais dentro de cada região de rede de chamam (CAC) do controle de admissão, E9-1-1 e implantações de bypass de mídia. Use os procedimentos neste artigo para configurar o controle de admissão de chamada para sites de rede.

## <a name="configure-network-site-links"></a>Configurar links de sites de rede

Em uma configuração (CAC) do controle de admissão de chamada, você pode criar políticas entre sites que definem limitações de largura de banda entre sites que estiverem diretamente ligados rede. Quando os sites de rede compartilham um link direto, as limitações de largura de banda para conexões de áudio e vídeos podem ser definidas entre esses dois sites. Você não pode usar o Skype para painel de controle do Business Server para configurar políticas de site de rede, isso pode ser feito apenas usando os cmdlets do Skype do Shell de gerenciamento do servidor de negócios. Você pode criar, modificar e remova um link de site de rede (também conhecido como uma política entre sites de rede) do Skype do Shell de gerenciamento do servidor de negócios.

### <a name="to-create-a-network-site-link"></a>Para criar um link de site de rede

1.  Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.

3.  No prompt de comando, digite o seguinte comando, substituindo os valores válidos para a sua configuração:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este exemplo cria um novo link de site de rede denominado Reno\_Portland que define limitações de largura de banda entre os sites de rede Reno e Portland. Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.

Para obter descrições detalhadas do parâmetro, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar uma lista de perfis de política de largura de banda que podem ser aplicadas a um link de site de rede, chame o cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar um link de site de rede

1.  Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.

3.  Use o cmdlet **Set-CsNetworkInterSitePolicy** para modificar as propriedades de um link de site de rede fornecido. Você pode modificar (ou ambas) ou os sites conectados e você pode modificar o perfil da política de largura de banda associado ao link. Aqui está um exemplo de modificar o perfil da política de largura de banda de um link de site denominado Reno\_Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obter descrições detalhadas do parâmetro, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para excluir um link de site de rede

1.  Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.

3.  Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede. O exemplo a seguir exclui o Reno\_link de site de rede de Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obter descrições detalhadas do parâmetro, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Exibir informações do site de rede

Os sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou Enhanced 9-1-1 de implantação. Você pode exibir informações do site de rede em ambos o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para exibir informações do site de rede no Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Site**.

4.  Na página do **Site** , clique no local que você deseja exibir.
 
    > [!NOTE]  
    > Você só pode exibir informações de um local por vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualizando informações de site de rede usando os cmdlets do Windows PowerShell

Você pode exibir informações do site de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkSite. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para exibir informações do site de rede

  - Para exibir informações sobre todos os sites de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkSite
    
    Isso retornará informações parecidas com:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Criar ou modificar sites de rede 

Os sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou Enhanced 9-1-1 de implantação. Você pode usar o Skype para painel de controle do Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede América do Norte pode ser associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede CAC deve ser criado para cada site dentro de uma organização, mesmo se esse site não tiver nenhuma limitação de largura de banda. O Skype para painel de controle do Business Server você pode criar, modificar e excluir sites de rede. Use os procedimentos a seguir para criar ou modificar um site de rede. 

### <a name="to-create-a-network-site"></a>Para criar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Site**.

4.  Na página do **Site** , clique em **novo**.

5.  Em **Novo Site**, digite um nome para este site no campo **nome** .

    > [!NOTE]  
    > Nomes de site devem ser exclusivos dentro do Skype para implantação de servidor de negócios.

6.  Na lista suspensa **região** , selecione uma região de rede para associar a este site.

7.  (Opcional) Se você deseja colocar as limitações de largura de banda em chamadas de áudio ou vídeos para esse site, selecione o perfil de política de largura de banda com as configurações apropriadas na lista suspensa **política de largura de banda** .
 
    > [!NOTE]  
    > Você pode exibir os detalhes dos perfis de política de largura de banda disponível ou criar um novo perfil de política de largura de banda, na página **Profil de diretiva** de grupo de **Configuração de rede** . Para obter detalhes, consulte [Gerenciando perfis de política de largura de banda de rede](managing-network-bandwidth-policy-profiles.md).

8.  (Opcional) Se você deseja fornecer configurações de localização para esse site, selecione uma política de local na lista suspensa **política de local** .

    > [!NOTE]  
    > A política de local atribui Enhanced 9-1-1 (E9-1-1) e cliente específicos configurações de local para o site. Você pode exibir os detalhes das diretivas de local disponíveis, ou criar uma nova política de local, na página **Política de local** do grupo de **Configuração de rede** . 

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse local, que não pode ser expressa somente pelo nome.

10. Clique em **Confirmar**.

    > [!NOTE]  
    > Você não usar a tabela de **Sub-redes associadas** ao criar um novo site de rede. Você pode associar uma sub-rede a um site quando você cria ou modifica a sub-rede. Para obter detalhes, consulte [Managing sub-redes da rede](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Para modificar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Site**.

4.  Na página do **Site** , clique no local que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar Site** , você pode modificar a descrição, região, perfil de política de largura de banda e política de local associadas ao site. Para obter detalhes, consulte [criar um site de rede](#to-create-a-network-site) acima.

7.  Clique em **Confirmar**.

Você não pode modificar a tabela de **Sub-redes associadas** nesta página. A lista de sub-redes associadas é fornecida para referência, de modo que você esteja ciente dos quais sub-redes serão afetados quando você modifica as configurações do site.


## <a name="delete-an-existing-network-site"></a>Excluir um site de rede existente

Os sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou Enhanced 9-1-1 de implantação. Você pode usar o Skype para painel de controle do Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede América do Norte pode ser associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede CAC deve ser criado para cada site dentro de uma organização, mesmo se esse site não tiver nenhuma limitação de largura de banda. O Skype para painel de controle do Business Server você pode criar, modificar e excluir sites de rede. Use o procedimento a seguir para excluir um site de rede existente. Para obter detalhes sobre como criar ou modificar sites de rede, consulte [Gerenciando o controle de admissão de chamada para sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Para excluir um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Site**.

4.  Na página do **Site** , clique no local que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um site por vez. Para fazer isso, pressione CTRL e selecione vários sites, mantendo pressionada a tecla CTRL. Ou, para selecionar todos os sites, clique em **Selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **Excluir**.

6.  Clique em **OK**.
    

    > [!WARNING]  
    > Se estiver associada a uma sub-rede de rede, é possível remover um site de rede. Se você tentar remover um local associado a uma sub-rede, você receberá uma mensagem de erro. Para ver se um site é associado a quaisquer sub-redes, clique no site e clique em **Mostrar detalhes** no menu **Editar** .


## <a name="see-also"></a>Consulte Também


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite.](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
