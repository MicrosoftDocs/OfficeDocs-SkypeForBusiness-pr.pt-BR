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
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359137"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server

Este tópico descreve como habilitar usuários para o Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .
  
- Para saber como configurar a conectividade híbrida, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business [Online.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- Para saber mais sobre como planejar sua implantação, consulte [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para saber mais sobre o Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamada [PSTN para o Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuários para o Sistema de Telefonia com conectividade PSTN local

Antes de mover seus usuários para o Skype for Business Online, é recomendável que você habilita seus usuários no local no Skype for Business Server ou no Lync Server 2013 e, em seguida, movê-los online. Para obter mais informações, consulte Planejar a conectividade híbrida entre o [Skype for Business Server](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e o Skype for Business Online e a seção de considerações especiais de Habilitar os usuários para o Enterprise [Voice](enable-the-users-for-enterprise-voice-on-premises.md) local (executado enquanto os usuários estão no local). 
  
Todos os usuários devem ser criados no Active Directory local e sincronizados com o Microsoft 365 ou o Office 365 usando a versão compatível do Azure AD Connector. Você não pode habilitar usuários para o Sistema de Telefonia no Office 365 que foram criados diretamente no Azure AD. Se você quiser habilitar o Sistema de Telefonia com conectividade PSTN local para um usuário que foi criado no Azure AD, será necessário criar uma nova conta para esse usuário no AD local, configurar a conta local e sincronizar a conta usando uma versão compatível da ferramenta Azure AD Connector. 
  
A habilitação de um usuário para o Sistema de Telefonia com conectividade PSTN local e, em seguida, a mudança para o Skype for Business Online requer as seguintes etapas:
  
- [Habilitar os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários estão no local).
    
- [Atribuir uma Política de Roteamento](assign-a-voice-routing-policy.md) de Voz (executada enquanto os usuários estão no local).
    
- [Sincronizar usuários com a nuvem e atribuir licenças (executadas](synchronize-users-to-the-cloud-and-assign-licenses.md) usando o Office 365).
    
- [Mova os usuários](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) locais para o Skype for Business Online (realizado usando o Windows PowerShell local, mas usando suas credenciais de administrador do Office 365).
    
- [Habilitar usuários para o Enterprise Voice Online e a Caixa Postal do Sistema de Telefonia](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realizado usando o PowerShell Remoto.
    

