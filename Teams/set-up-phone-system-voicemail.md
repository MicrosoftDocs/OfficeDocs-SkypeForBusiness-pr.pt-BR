---
title: Configurar a caixa postal na nuvem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar a caixa postal de nuvem para seus usuários. '
ms.openlocfilehash: 3f8729c9737bcbf0e7731ac61b38d56d708e15dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204789"
---
# <a name="set-up-cloud-voicemail"></a>Configurar a caixa postal na nuvem

Este artigo destina-se o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal de nuvem para que todos na empresa.

> [!NOTE]
> Caixa postal de nuvem oferece suporte a mensagens de caixa postal depositar somente em uma caixa de correio do Exchange e não tem suporte para qualquer sistemas de email de terceiros. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Ambientes somente em nuvem: configurar a caixa postal de nuvem

Skype para usuários corporativos Online e planos de chamada, caixa postal de nuvem é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.
  
1. Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** . Você também pode precisar adquirir uma licença do Exchange Online. Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), as [equipes da Microsoft atribuir licenças](assign-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa. Depois disso, elas poderão receber mensagens de voz!
    
3. Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

## <a name="phone-system-with-on-premises-environments"></a>Sistema de Telefonia com ambientes locais

As seguintes informações são sobre como configurar a caixa postal de nuvem para funcionar com ambientes de chamar planejar locais.
  
1. Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** . Você também precisará comprar uma licença do Exchange Online. Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), as [equipes da Microsoft atribuir licenças](assign-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.
    
3. Siga as instruções correspondentes PSTN local chamando a solução implantada para seus usuários. Edition do conector de nuvem, siga as instruções na seção **habilitar usuários para serviços de caixa postal e voz do sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/library/mt605228.aspx). Para chamar com Skype para Business Server PSTN, siga a [habilitar os usuários para o Enterprise Voice no local](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Roteamento direto de equipes, siga a seção **Configurar o número de telefone e habilitar enterprise voice e caixa postal** de [Configurar o roteamento direto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).

4. Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

5. Mensagens de caixa postal são entregues a caixa de correio do Exchange dos usuários por meio do SMTP roteada por meio do Exchange Online Protection. Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores do Exchange estão configurados corretamente entre seus servidores Exchange e o Exchange Online Protection. [Conectores de uso para configurar o fluxo de emails](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

6. Para habilitar os recursos de caixa postal como personalizando saudações e caixa postal visual no Skype para clientes corporativos, é necessária a conectividade do Office 365 para caixa postal do Exchange server por meio de serviços Web do Exchange. Para habilitar essa conectividade, você deve configurar o novo Oauth do Exchange descrevem do protocolo de autenticação em [Configure OAuth authentication entre organizações do Exchange e o Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) 

> [!NOTE]
> O Assistente de híbrida do Exchange execução do Exchange 2013 CU5 ou superior lidará com os requisitos nas etapas 5 e 6 automaticamente. 

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

> [!IMPORTANT]
> Não é possível criar uma nova instância de política para a transcrição e obscenidades transcrição mascaramento usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para fazer isso, execute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Para fazer isso, execute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

Para desabilitar a transcrição para um único usuário, execute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativação do mascaramento de obscenidades para um usuário

Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para habilitar o mascaramento de obscenidades para um único usuário, execute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business

Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios. Indique os seguintes artigos:

- [Verificar Skype para opções e caixa postal de negócios](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.

- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Plano de migração para o Skype for Business Server e Exchange Server](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


