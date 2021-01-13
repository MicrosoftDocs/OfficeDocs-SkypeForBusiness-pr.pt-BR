---
title: Habilitando o controle de admissão de chamada
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
description: " Depois de configurar a rede cac (controle de admissão de chamada), você deve habilitar o CAC para impor as limitações de largura de banda."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816501"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar o controle de admissão de chamada no Skype for Business Server

O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede CAC, habilite o CAC para impor as limitações de largura de banda. Você pode usar o Painel de Controle do Skype for Business Server para fazer isso.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar o CAC no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**

4.  Na página **Global**, clique na configuração **Global**.
   
    > [!NOTE]  
    > Apenas uma rede pode ser configurada para qualquer implantação do Skype for Business Server, portanto, nunca haverá mais de uma configuração de rede na lista. Você não pode renomear a configuração Global.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Configuração Global**, marque a caixa de seleção **Habilitar controle de admissão de chamadas** e então clique em **Confirmar**.

Quando você clica em **Confirmar**, você executa um teste da configuração. A caixa de diálogo **Editar Configurações Globais** é fechada, retornando você à página **Global**. Você receberá uma viso sobre qualquer erro ou inconsistência descoberta em sua configuração de rede que a impeça de funcionar corretamente (por exemplo, se cada região não estiver conectada às outras regiões através de uma rota intrarregional).

Caso faça alterações em sua configuração de rede, você pode executar a verificação de validação novamente abrindo a configuração Global e clicando em **Confirmar**. Você não precisa desativar o CAC primeiro: deixe a caixa de seleção marcada e clique em **Confirmar**. Você pode fazer isso a qualquer hora sem fazer nenhuma alteração na configuração.

## <a name="see-also"></a>Confira também

[Planejar o controle de admissão de chamada](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implantar o serviço de controle de admissão de chamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
