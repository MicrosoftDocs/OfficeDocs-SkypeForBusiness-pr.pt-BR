---
title: Habilitando o controle de admissão de chamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Depois de configurar a rede de controle de admissão de chamadas (CAC), você deve habilitar o CAC para impor as limitações de largura de banda."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817530"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar o controle de admissão de chamada no Skype for Business Server

O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Depois de configurar a rede do CAC, você deve habilitar o CAC para impor as limitações de largura de banda. Você pode usar o painel de controle do Skype for Business Server para fazer isso.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar o CAC no painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **global**.

4.  Na página **global** , clique em configuração **global** .
   
    > [!NOTE]  
    > Somente uma rede pode ser configurada para qualquer implantação do Skype for Business Server, portanto, nunca haverá mais de uma configuração de rede na lista. Não é possível renomear a configuração global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar configuração global** , marque a caixa de seleção **habilitar controle de admissão de chamadas** e clique em **confirmar**.

Quando você clica em **confirmar**, executa um teste de configuração. A caixa de diálogo **Editar configurações globais** é fechada, retornando você à página **global** . Você receberá um aviso se quaisquer erros ou inconsistências forem descobertos em sua configuração de rede que o impedirá de funcionar corretamente (por exemplo, se cada região não estiver conectada a todas as outras regiões por meio de uma rota entre regiões).

Se você fizer alterações em sua configuração de rede, poderá executar a verificação de validação novamente abrindo a configuração global e clicando em **confirmar**. Você não precisa desabilitar o CAC primeiro: Deixe a caixa de seleção marcada e clique em **confirmar**. Você pode fazer isso a qualquer momento sem fazer alterações de configuração.

## <a name="see-also"></a>Confira também

[Planejamento do controle de admissão de chamadas](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implantar o serviço de controle de admissão de chamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
