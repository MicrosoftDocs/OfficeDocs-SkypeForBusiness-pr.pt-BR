---
title: Configurar a caixa postal do Sistema de Telefonia
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
description: 'Aprenda como configurar a caixa postal do sistema de telefonia (Cloud PBX) para seus usuários do Skype for Business. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252885"
---
# <a name="set-up-phone-system-voicemail"></a>Configurar a caixa postal do Sistema de Telefonia

Este artigo destina-se ao [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de caixa postal do Sistema de Telefonia para todos na empresa.

> [!NOTE]
> A caixa postal do Sistema de Telefonia só suporta depositar mensagens de voz em uma caixa de correios do Exchange, mas não dá suporte a nenhum sistema de email de terceiros. Como um mecanismo de fallback, a caixa postal do Sistema de Telefonia pode reenviar mensagens usando SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberão suas mensagens de voz sem serviço garantido de uptime ou outros recursos de caixa postal, como alterar as saudações e outras configurações.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Ambientes somente em nuvem: configurar a caixa postal do Sistema de Telefonia

Para o Skype for Business Online e usuários de planos de chamada, a caixa postal do Sistema de Telefonia é automaticamente configurada e provisionada para usuários depois que você atribuir uma licença do **Sistema de Telefonia** e um número de telefone para acessá-los.

1. Se o recurso de Sistema de Telefonia não estiver incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema de Telefonia**. Você também precisará comprar uma licença do Exchange Online. Confira [Licenciamento de complementos do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Atribuir ou remover licenças de assinatura no Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e as licenças do Exchange Online para as pessoas da sua empresa. Depois disso, elas poderão receber mensagens de voz!

3. O suporte para transcrição da caixa postal foi incluído a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

## <a name="phone-system-with-on-premises-environments"></a>Sistema de Telefonia com ambientes locais

As seguintes informações são sobre como configurar a caixa postal do Sistema de Telefonia para funcionar com ambientes de Planos de Chamada locais.

1. Se o recurso de Sistema de Telefonia não estiver incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema de Telefonia**. Você também precisará comprar uma licença do Exchange Online. Confira [Licenciamento de complementos do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Atribuir ou remover licenças de assinatura no Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e as licenças do Exchange Online para as pessoas da sua empresa.

3. Depois, siga as instruções na seção **Habilitar usuários para os serviços de caixa postal e de voz do Sistema de Telefonia** seção do [guia Configurar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. O suporte para transcrição da caixa postal foi incluído a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários. Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.

5. Você também pode ver a [suporte da caixa postal do Azure para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal do Azure para usuários do Sistema de Telefonia que possuem caixas de correio locais.

## <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).

> [!IMPORTANT]
> Você não pode criar uma nova instância para transcrição e mascaramento de obscenidades usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não pode remover uma instância existente de política usando o cmdlet **Remove-CsOnlineVoiceMailPolicy**.

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para transcrição é ativada para sua organização, talvez você deseje desativá-la usando o cdmlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para isso, execute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Para isso, execute:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal for habilitada para todos os usuários, você pode atribuir uma política para desativar a transcrição de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Para desativar a transcrição para um único usuário, execute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativação do mascaramento de obscenidades para um usuário

Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).

Para habilitar o mascaramento de obscenidades para um único usuário, execute:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> [!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ajude seus usuários a conhecerem os recursos da caixa postal do Skype for Business

Há uma grande quantidade de informação de treinamento e artigos para ajudar os usuários a terem êxito com a caixa postal do Skype for Business. Indique os seguintes artigos:

- [Verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): este artigo explica como ouvir as mensagens da caixa postal no Skype for Business, alterar a saudação da caixa postal e ouvir as mensagens da caixa postal em diferentes velocidades.

- [Treinamento do Skype for Business 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


