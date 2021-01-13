---
title: Gerenciando o controle de admissão de chamada para sites
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Os sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia.
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816451"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gerenciando o controle de admissão de chamadas para sites no Skype for Business Server

Os sites de rede são os escritórios ou locais em cada região de rede do controle de admissão de chamadas (CAC), E9-1-1 e implantações de bypass de mídia. Use os procedimentos neste artigo para configurar o controle de admissão de chamada para sites de rede.

## <a name="configure-network-site-links"></a>Configurar links de site de rede

Em uma configuração de controle de admissão de chamada, você pode criar políticas entre locais de rede que definem as limitações de largura de banda entre os locais que estejam diretamente vinculados. Quando os locais de uma rede compartilham um link direto, é possível definir limitações de largura de banda às conexões audiovisuais entre esses dois locais. Não é possível usar o Painel de Controle do Skype for Business Server para configurar políticas de site de rede, isso só pode ser feito usando cmdlets do Shell de Gerenciamento do Skype for Business Server. Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de Gerenciamento do Skype for Business Server.

### <a name="to-create-a-network-site-link"></a>Para criar um link de site de rede

1.  Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**

3.  No prompt de comando, digite o seguinte comando, substituindo os valores que são válidos para a sua configuração:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este exemplo cria um novo link de site de rede chamado Reno Portland que define limitações de largura de banda entre os sites de rede Reno e \_ Portland. Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.

Para descrições detalhadas dos parâmetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Para recuperar uma lista de perfis de políticas de largura de banda que podem ser aplicada ao link de site de rede, chame o cmdlet de **Get-CsNetworkBandwidthPolicyProfile**. Para obter detalhes, [consulte Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Para modificar um link de site de rede

1.  Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**

3.  Use o cmdlet **Set-CsNetworkInterSitePolicy** para modificar as propriedades de um link de site de rede fornecido. Você pode modificar um (ou ambos) dos sites conectados e modificar o perfil da política de largura de banda associado ao link. Aqui está um exemplo de modificação do perfil de política de largura de banda de um link de site chamado Reno \_ Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para descrições detalhadas de parâmetros, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Para excluir um link de site de rede

1.  Faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários.

2.  Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**

3.  Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede. O exemplo a seguir exclui o link de site de rede Reno \_ Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para descrições detalhadas de parâmetros, [consulte Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Exibir informações de site de rede

Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado. Você pode exibir informações do site de rede no Painel de Controle do Skype for Business Server ou no Shell de Gerenciamento do Skype for Business Server. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Para exibir informações do site de rede no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**

4.  Na página **Local**, clique no local que deseja exibir.
 
    > [!NOTE]  
    > É possível exibir apenas informações de um local por vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de site de rede usando cmdlets do Windows PowerShell

Você pode exibir informações do site de rede usando o Windows PowerShell e o Get-CsNetworkSite cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Para exibir a informação do local de rede

  - Para exibir informações sobre todos os seus sites de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkSite
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).


## <a name="create-or-modify-network-sites"></a>Criar ou modificar sites de rede 

Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado. Você pode usar o Painel de Controle do Skype for Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver. Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda. No Painel de Controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede. Use os procedimentos a seguir para criar ou modificar um site da rede. 

### <a name="to-create-a-network-site"></a>Para criar um local de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**

4.  Na página **Local**, clique em **Novo**.

5.  Em **Novo Local**, digite um nome para este local no campo **Nome**.

    > [!NOTE]  
    > Os nomes de site devem ser exclusivos na implantação do Skype for Business Server.

6.  Na lista suspensa **Região**, selecione uma região da rede para associar a este local.

7.  (Opcional) Se deseja impor limitações de largura de banda em chamadas de áudio ou vídeo para este local, selecione o perfil da política da largura de banda com as configurações apropriadas na lista suspensa **Política da largura de banda**.
 
    > [!NOTE]  
    > Você pode exibir os detalhes dos perfis de política de largura de banda disponíveis ou criar um novo perfil de política de largura de banda na página **Profil** de Política do grupo **Configuração de** Rede. Para obter detalhes, consulte [Gerenciando perfis de política de largura de banda de rede.](managing-network-bandwidth-policy-profiles.md)

8.  (Opcional) Se deseja fornecer configurações de localização para esse local, selecione uma política de localização na lista suspensa **Política de localização**.

    > [!NOTE]  
    > A política de localização atribui configurações específicas de 9-1-1 Aprimorado (E9-1-1) e de localização do cliente ao local. Você pode ver os detalhes das políticas de localização disponíveis ou criar uma política nova na página **Política de localização** do grupo **Configuração de Rede**. 

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse local, que não podem ser expressadas apenas pelo nome.

10. Clique em **Comprometer**.

    > [!NOTE]  
    > Você não usa a tabela **Sub-redes Associadas** ao criar um novo local de rede. Você associa a sub-rede ao local quando criá-la ou modificá-la. Para obter detalhes, consulte [Gerenciando sub-redes de rede.](managing-network-subnets.md)

### <a name="to-modify-a-network-site"></a>Para modificar um local de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**

4.  Na página **Local**, clique no local que deseja modificar.

5.  No painel **Ações**, clique em **Mostrar detalhes**.

6.  Na página **Editar Local**, você pode modificar a descrição, região, perfil da política da largura de banda e política de localização associados ao novo local. Para obter detalhes, [consulte Para criar um site de rede](#to-create-a-network-site) acima.

7.  Clique em **Comprometer**.

Você não pode modificar a tabela **Sub-redes Associadas** nesta página. A lista de sub-redes associadas é fornecida para referência, para que você saiba quais sub-redes serão afetadas quando você modificar as configurações do local.


## <a name="delete-an-existing-network-site"></a>Excluir um site de rede existente

Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado. Você pode usar o Painel de Controle do Skype for Business Server para configurar sites e associá-los a regiões. Por exemplo, uma região de rede da América do Norte pode ser associada a sites da rede, como Chicago, Redmond e Vancouver. Um site da rede do CAC deve ser criado para cada site da organização, mesmo que esse site não tenha limitações de largura de banda. No Painel de Controle do Skype for Business Server, você pode criar, modificar e excluir sites de rede. Use o seguinte procedimento para excluir um local de rede existente. Para obter detalhes sobre como criar ou modificar sites de rede, consulte [Gerenciando o controle de admissão de chamada para sites.](managing-call-admission-control-for-sites.md)


### <a name="to-delete-a-network-site"></a>Para excluir um local de rede

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Site.**

4.  Na página **Local**, clique no local que deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um local de cada vez. Para fazer isso, pressione CTRL e selecione diversos locais mantendo a tecla pressionada. Ou então, para selecionar todos os locais, clique em **Selecionar Tudo** no menu **Editar**.

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.
    

    > [!WARNING]  
    > Você não poderá remover um local de rede se ele estiver associado a uma sub-rede. Se você tentar fazer isso, receberá uma mensagem de erro. Para ver se o local está associado a alguma sub-rede, clique no local e em **Mostrar detalhes** no menu **Editar**.


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
