---
title: Configurar a caixa postal do sistema telefônico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 93dd33eefe587c548e346974cc86fe2608b392ec
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="set-up-phone-system-voicemail"></a>Configurar a caixa postal do sistema telefônico

Este artigo destina-se o [administrador do Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal do sistema telefônico para que todos na empresa.
  
> [!NOTE]
> Caixa postal do sistema telefônico oferece suporte a mensagens de caixa postal depositar somente em uma caixa de correio do Exchange e não tem suporte para qualquer sistemas de email de terceiros. Como um mecanismo de fallback, caixa postal do sistema telefônico pode reenviar mensagens usando o SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberá suas mensagens de caixa postal com nenhum tempo de atividade do serviço garantido ou outros recursos de caixa postal, como a alteração suas saudações e outras configurações. 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Ambientes somente em nuvem: configurar a caixa postal do sistema telefônico

Skype para usuários corporativos Online e planos de chamada, caixa postal do sistema telefônico é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.
  
1. Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** . Você também pode precisar adquirir uma licença do Exchange Online. Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa. Depois disso, elas poderão receber mensagens de voz!
    
3. Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações. Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.
    
## <a name="phone-system-with-on-premises-environments"></a>Sistema telefônico com ambientes locais

As seguintes informações são sobre como configurar a caixa postal do sistema telefônico para funcionar com ambientes de chamar planejar locais.
  
1. Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** . Você também precisará comprar uma licença do Exchange Online. Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.
    
3. Siga as instruções na seção **habilitar usuários para serviços de correio de voz e voz de sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações. Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo. 
    
5. Você também pode ver a [caixa postal do Azure PBX suporte para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal Azure para usuários de sistema telefônico que possuem um caixas de correio local.
    
## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

Transcrição do correio de voz é habilitada por padrão e mascaramento de obscenidades transcrição está desabilitado por padrão para todas as organizações e usuários; No entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> Não é possível criar uma nova instância de política para a transcrição e obscenidades transcrição mascaramento usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .
  
Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para fazer isso, execute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativando o mascaramento de obscenidades transcrição para sua organização

Mascaramento de obscenidades transcrição está desabilitado por padrão para sua organização. Se houver um requisitos de negócios para habilitá-lo, você pode habilitar obscenidades transcrição mascaramento usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para fazer isso, execute:
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .
  
Para desabilitar a transcrição para um único usuário, execute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativando o mascaramento de obscenidades transcrições de um usuário

Para habilitar o mascaramento de obscenidades transcrição para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Para habilitar obscenidades transcrição mascaramento de um único usuário, execute:
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas. 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios. Indique os seguintes artigos:
  
- [Verificar Skype para opções e caixa postal de negócios](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.
    
- [Treinamento do Skype for Business 2016](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 