---
title: Habilitar o controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilite o controle de admissão de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: c5fc500b4e0839b4db43bd229087b3a6bcc7e644
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767284"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar o controle de admissão de chamadas no Skype for Business Server
 
Habilite o controle de admissão de chamadas no Skype for Business Server Enterprise Voice. 
  
Após definir as configurações de rede para a implantação do serviço de controle de admissão de chamadas, habilite o CAC para que as políticas de largura de banda entrem em vigor.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar o controle de admissão de chamadas usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet Set-CsNetworkConfiguration para ativar o CAC na rede. Por exemplo, execute:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Se você deseja desativar o CAC na rede, execute o seguinte:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar o controle de admissão de chamadas usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique no botão de navegação **Global**.
    
4. Clique em **Global** na lista e selecione **Exibir detalhes** no menu **Editar**.
    
5. Na página **Editar Configurações Globais**, marque a caixa de seleção **Ativar controle de admissão de chamada**.
    
    > [!NOTE]
    > Se você deseja desativar o controle de admissão de chamada durante a implantação, desmarque esta caixa de seleção. 
  
6. Clique em **Confirmar**. 
    
## <a name="see-also"></a>Confira também

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
