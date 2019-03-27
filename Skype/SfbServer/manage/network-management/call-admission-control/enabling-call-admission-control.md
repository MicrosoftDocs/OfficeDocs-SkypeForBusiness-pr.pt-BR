---
title: Habilitando o controle de admissão de chamada
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Depois de configurar a rede de (CAC) do controle de admissão de chamada, você deve habilitar o CAC para impor as limitações de largura de banda."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897640"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar o controle de admissão de chamada no Skype for Business Server

O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Depois de configurar a rede CAC, você deve habilitar o CAC para impor as limitações de largura de banda. Você pode usar o Skype para painel de controle do Business Server para fazer isso.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar o CAC do Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.

4.  Na página **Global** , clique na configuração **Global** .
   
    > [!NOTE]  
    > Apenas uma rede pode ser configurada para qualquer Skype para implantação de servidor de negócios, portanto nunca haverá mais de uma configuração de rede na lista. Não é possível renomear na configuração Global.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar configuração Global** , marque a caixa de seleção **Habilitar controle de admissão de chamada** e clique em **Confirmar**.

Quando você clica **em Confirmar**, você executa um teste da configuração. Fecha a caixa de diálogo **Editar configurações globais** , retornando à página **Global** . Você receberá um aviso se existem erros ou inconsistências são descobertas na sua configuração de rede que impede que ele funcionando corretamente (por exemplo, se cada região não estiver conectada a outra região por meio de uma rota entre regiões).

Se você fizer alterações à sua configuração de rede, você pode executar a verificação de validação abrindo na configuração Global e clicando em **Confirmar**. Você não precisa desativar o CAC: deixe a caixa de seleção marcada e clique em **Confirmar**. Você pode fazer isso a qualquer momento sem fazer quaisquer alterações de configuração.

## <a name="see-also"></a>Consulte Também

[Planejamento do controle de admissão de chamadas](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implantar o serviço de controle de admissão de chamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
