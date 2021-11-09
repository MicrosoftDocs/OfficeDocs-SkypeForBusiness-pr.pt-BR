---
title: Gerenciando regiões de rede
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Região de rede* são os hubs de rede ou backbones usados na configuração do controle de admissão de chamada, E9-1-1 e desvio de mídia.
ms.openlocfilehash: 5d0a40576098ceb641bdc677a551908b6a23044b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843864"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gerenciando regiões de rede no Skype for Business Server

*Regiões de rede* são hubs de rede ou backbones usados na configuração do serviço de controle de admissão de chamadas, E9-1-1 e desvio de mídia. Use os procedimentos a seguir para visualizar, criar ou modificar regiões de rede. Por exemplo, se você já criou regiões de rede para um recurso de Voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede. Porém, talvez seja necessário modificar uma definição de região de rede existente para aplicar configurações específicas ao recurso. Por exemplo, se você cria regiões de rede para o E9-1-1 (que não exige um local central associado) e depois implanta o controle de admissão de chamadas, precisará modificar as definições de região de rede para especificar um local central. 

Use os procedimentos deste artigo para exibir informações da região de rede ou criar, modificar ou excluir regiões de rede. 

## <a name="view-network-region-information"></a>Exibir informações da região de rede 


Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar Skype for Business Server Painel de Controle para exibir regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. Use este tópico para exibir regiões de rede existentes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para exibir informações sobre uma região de rede com Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Região**.

4.  Na página **Região,** clique na região que você deseja exibir.
  
    > [!NOTE]  
    > Você só pode exibir uma região por vez.

5.  No painel **Ações**, clique em **Mostrar detalhes**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de região de rede usando Windows PowerShell cmdlets

Você pode exibir informações da região de rede usando Windows PowerShell e o cmdlet **Get-CsNetworkRegion.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para exibir informações da região de rede

  - Para exibir informações sobre todas as regiões de rede, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
    **Get-CsNetworkRegion**
    
    Isto retorna informações semelhantes à seguinte:
    
    Identidade : Noroeste do Pacífico<br/>
    Descrição :<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite : Site:Redmond1<br/>
    BWAlternatePaths : {BWPolicyModality=Audio; AlternatePath=True, <br/>
                       BWPolicyModality=Video; AlternatePath=True}<br/>
    NetworkRegionID : Noroeste do Pacífico<br/>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion.](/powershell/module/skype/Get-CsNetworkRegionLink)


## <a name="create-or-modify-network-regions"></a>Criar ou modificar regiões de rede 

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar o painel de controle Skype for Business Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. No painel Skype for Business Server controle, você pode criar, modificar ou excluir uma região de rede. Use este tópico para criar e modificar regiões de rede. 

### <a name="to-create-a-network-region"></a>Para criar uma região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Região**.

4.  Na página **Região**, clique em **Novo**.

5.  Na página **Nova Região**, digite um valor no campo **Nome**. Esse valor deve ser exclusivo em sua Skype for Business Server implantação.

6.  Na lista suspensa **Site central**, selecione o site central para essa região de rede.

7.  A caixa de seleção **Habilitar caminho alternativo do áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.

8.  A caixa de seleção **Habilitar caminho alternativo do vídeo** está marcada por padrão. Esse campo determina se as chamadas de vídeo serão roteadas por um caminho alternativo, caso a largura de banda adequada não exista no caminho primário. Desmarque essa caixa de seleção somente se precisar desativar o descarregamento para a Internet. Se qualquer uma de suas chamadas for uma chamada pela Internet, essa caixa de seleção deverá ser marcada, independente das configurações de largura de banda.

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não podem ser expressas somente pelo nome.

10. Clique em **Confirmar**.

A tabela **Sites associados** não é usada para criar uma região de rede. Você associa um site a uma região quando cria ou modifica o site. Para obter detalhes, consulte [Managing call admission control for sites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Para modificar uma região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Região**.

4.  Na página **Região**, clique na região que você deseja modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Região**, é possível modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "Para criar uma região de rede" acima neste tópico.

7.  Clique em **Confirmar**.

Não é possível modificar os **Sites associados** nesta página. A lista de sites associados é fornecida para referência de modo que você fique ciente de quais sites serão afetados quando você modificar as configurações de região.


## <a name="delete-existing-network-regions"></a>Excluir regiões de rede existentes 

Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas. Cada região de rede deve ser associada com um local central. O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando. Você pode usar o painel de controle Skype for Business Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo. No painel Skype for Business Server controle, você pode criar, modificar ou excluir uma região de rede. Use este tópico para excluir regiões de rede existentes. 

### <a name="to-delete-a-network-region"></a>Para excluir uma região de rede

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Região**.

4.  Na página **Região**, clique na região que você deseja excluir.
  
    > [!NOTE]  
    > É possível excluir mais de uma região por vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém pressionada a tecla CTRL. Ou, para selecionar todas as regiões, clique em **Selecionar tudo** no menu **Editar**.

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.


    > [!WARNING]  
    > Uma região de rede não pode ser removida se estiver associada a um site de rede. Se você tentar remover uma região associada a um site, receberá uma mensagem de erro. Para ver se um região está associada a algum site, selecione a região e clique em **Mostrar detalhes** no menu **Editar**.


## <a name="see-also"></a>Confira também

[Gerenciando rotas de região de rede](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)