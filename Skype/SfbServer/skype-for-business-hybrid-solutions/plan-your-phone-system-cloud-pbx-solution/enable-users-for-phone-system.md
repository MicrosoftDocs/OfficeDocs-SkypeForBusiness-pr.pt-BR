---
title: Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'Este tópico descreve como habilitar usuários para o Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120863"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server

Este tópico descreve como habilitar usuários para o Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .
  
- Para saber como configurar a conectividade híbrida, consulte Plan hybrid [connectivity between Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and Skype for Business Online and [Deploy hybrid connectivity between Skype for Business Server](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)and Skype for Business Online .
    
- Para saber mais sobre como planejar sua implantação, consulte [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para saber mais sobre o Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamadas [PSTN para Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021 após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuários para o Sistema de Telefonia com conectividade PSTN local

Antes de mover seus usuários para o Skype for Business Online, é recomendável habilitar seus usuários no local no Skype for Business Server ou no Lync Server 2013 e movê-los online. Para obter mais informações, consulte Plan [hybrid connectivity between Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and Skype for Business Online and the special considerations section of Enable the users for Enterprise Voice on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises). 
  
Todos os usuários devem ser criados no Active Directory local e sincronizados com o Microsoft 365 ou o Office 365 usando a versão suportada do Conector do Azure AD. Você não pode habilitar usuários para o Sistema de Telefonia no Office 365 que foram criados diretamente no Azure AD. Se você quiser habilitar o Sistema de Telefonia com conectividade PSTN local para um usuário criado no Azure AD, será necessário criar uma nova conta para esse usuário no AD local, configurar a conta local e sincronizar a conta usando uma versão suportada da ferramenta conector do Azure AD. 
  
Habilenciar um usuário para o Sistema de Telefonia com conectividade PSTN local e, em seguida, habilita-lo para o Skype for Business Online requer as seguintes etapas:
  
- [Habilitar os usuários para Enterprise Voice local (executados](enable-the-users-for-enterprise-voice-on-premises.md) enquanto os usuários estão em casa no local).
    
- [Atribua uma Política de Roteamento](assign-a-voice-routing-policy.md) de Voz (executada enquanto os usuários estão no local).
    
- [Sincronizar usuários com a nuvem e atribuir licenças (executadas](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) usando o Office 365).
    
- [Mova os usuários locais](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) para o Skype for Business Online (executado usando Windows PowerShell local, mas usando suas credenciais de administrador do Office 365).
    
- [Habilitar usuários para Enterprise Voice online e Caixa](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) Postal do Sistema de Telefonia (realizada usando o PowerShell Remoto.
