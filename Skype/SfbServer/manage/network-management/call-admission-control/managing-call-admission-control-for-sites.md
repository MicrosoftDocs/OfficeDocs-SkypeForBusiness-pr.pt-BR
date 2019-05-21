---
title: Gerenciando o controle de admissão de chamadas para sites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279540"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gerenciar o controle de admissão de chamadas para sites no Skype for Business Server

Sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia. Use os procedimentos deste artigo para configurar o controle de admissão de chamadas para sites de rede.

## <a name="configure-network-site-links"></a>Configurar links de sites de rede

Em uma configuração de controle de admissão de chamadas (CAC), você pode criar políticas entre sites de rede que definem as limitações de largura de banda entre sites vinculados diretamente. Quando os sites de rede compartilham um link direto, as limitações de largura de banda para conexões de áudio e vídeo podem ser definidas entre esses dois sites. Você não pode usar o painel de controle do Skype for Business Server para configurar políticas de site de rede, isso pode ser feito somente usando cmdlets do Shell de gerenciamento do Skype for Business Server. Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de gerenciamento do Skype for Business Server.

### <a name="to-create-a-network-site-link"></a>Para criar um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

3.  No prompt de comando, digite o comando a seguir, substituindo os valores válidos para a sua configuração:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este exemplo cria um novo link de site de rede\_chamado Reno Portland que define as limitações de largura de banda entre os sites de rede Reno e Portland. Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.

Para obter descrições de parâmetros detalhadas, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar uma lista de perfis de política de largura de banda que podem ser aplicados ao link de site de rede, chame o cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

3.  Use o cmdlet **set-CsNetworkInterSitePolicy** para modificar as propriedades de um determinado link de site de rede. Você pode modificar um (ou ambos) ou os sites conectados, e pode modificar o perfil da política de largura de banda associado ao link. Aqui está um exemplo de modificação do perfil da política de largura de banda de um\_link de site chamado Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obter descrições de parâmetros detalhadas, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para excluir um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

3.  Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede. O exemplo a seguir exclui o\_link de site de rede de Portland Reno:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obter descrições de parâmetros detalhadas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Exibir informações do site de rede

Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada. Você pode exibir as informações do site de rede no painel de controle do Skype for Business Server ou no Shell de gerenciamento do Skype for Business Server. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para ver as informações do site de rede no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja exibir.
 
    > [!NOTE]  
    > Você só pode exibir informações de um site de cada vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Exibir informações do site de rede usando cmdlets do Windows PowerShell

Você pode exibir informações do site de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkSite. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para ver as informações do site de rede

  - Para ver informações sobre todos os seus sites de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkSite
    
    Isso retornará informações parecidas com:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Criar ou modificar sites de rede 

Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada. Você pode usar o painel de controle do Skype for Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede. Use os procedimentos a seguir para criar ou modificar um site de rede. 

### <a name="to-create-a-network-site"></a>Para criar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.

4.  Na página do **site** , clique em **novo**.

5.  Em **novo site**, digite um nome para este site no campo **nome** .

    > [!NOTE]  
    > Os nomes dos sites devem ser exclusivos na implantação do Skype for Business Server.

6.  Na lista suspensa **região** , selecione uma região de rede para associar a este site.

7.  Adicionais Se você quiser colocar as limitações de largura de banda em chamadas de áudio ou vídeo para este site, selecione o perfil da política de largura de banda com as configurações apropriadas na lista suspensa **política de largura de banda** .
 
    > [!NOTE]  
    > Você pode exibir os detalhes dos perfis da política de largura de banda disponíveis ou criar um novo perfil de política de largura de banda na página **Profil da política** do grupo **configuração de rede** . Para obter detalhes, consulte [Gerenciando perfis da política de largura de banda de rede](managing-network-bandwidth-policy-profiles.md).

8.  Adicionais Se você quiser fornecer configurações de localização para este site, selecione uma política de localização na lista suspensa **política de localização** .

    > [!NOTE]  
    > A política de localização atribui configurações de localização avançada de 9-1-1 (E9-1-1) e de cliente de cliente (-1-1) específicas ao site. Você pode exibir os detalhes das políticas de localização disponíveis ou criar uma nova política de localização, na página **política de localização** do grupo de **configuração de rede** . 

9.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse site que não pode ser expresso apenas pelo nome.

10. Clique em **Confirmar**.

    > [!NOTE]  
    > Você não usa a tabela de **sub-redes associadas** quando cria um novo site de rede. Você associa uma sub-rede a um site quando cria ou modifica a sub-rede. Para obter detalhes, consulte [Gerenciando sub-redes de rede](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Para modificar um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar site** , você pode modificar a descrição, a região, o perfil da política de largura de banda e a política de localização associada ao site. Para obter detalhes, consulte [criar um site de rede](#to-create-a-network-site) acima.

7.  Clique em **Confirmar**.

Não é possível modificar a tabela de **sub-redes associadas** nesta página. A lista de sub-redes associadas é fornecida para referência para que você saiba quais são as sub-redes que serão afetadas quando você modificar as configurações do site.


## <a name="delete-an-existing-network-site"></a>Excluir um site de rede existente

Sites de rede são os escritórios ou locais configurados em cada região de um controle de admissão de chamadas (CAC) ou implantação 9-1-1 aprimorada. Você pode usar o painel de controle do Skype for Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede para a América do Norte pode estar associada a sites de redes como Chicago, Redmond e Vancouver. Um site de rede do CAC deve ser criado para cada site dentro de uma organização, mesmo que esse site não tenha limitações de largura de banda. No painel de controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede. Use o procedimento a seguir para excluir um site de rede existente. Para obter detalhes sobre como criar ou modificar sites de rede, consulte Gerenciando o [controle de admissão de chamadas para sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Para excluir um site de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **site**.

4.  Na página do **site** , clique no site que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um site de cada vez. Para fazer isso, pressione CTRL e selecione vários sites enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os sites, clique em **selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.
    

    > [!WARNING]  
    > Você não pode remover um site de rede se ele estiver associado a uma sub-rede de rede. Se você tentar remover um site associado a uma sub-rede, receberá uma mensagem de erro. Para ver se um site está associado a qualquer sub-rede, clique no site e, em seguida, clique em **Mostrar detalhes** no menu **Editar** .


## <a name="see-also"></a>Confira também


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
