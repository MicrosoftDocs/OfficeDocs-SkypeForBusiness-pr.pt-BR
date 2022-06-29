---
title: Alterar o idioma padrão de saudações e emails
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Saiba como configurar o Microsoft Teams e Skype for Business usar outro idioma para a saudação da caixa postal padrão da sua organização.
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241120"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>Alterar o idioma padrão de saudações e emails

Caixa postal na Nuvem usa várias configurações de idioma para reproduzir saudações, gerar traduções de transcrição e gerar mensagens de caixa postal. As configurações de idioma podem ser especificadas por padrão no nível do locatário, por política ou individualmente em um determinado usuário.

## <a name="greetings"></a>Saudações
As saudações são executadas para o chamador deixando a caixa postal e podem ser os seguintes tipos:

- Saudações do sistema
- Saudações personalizadas registradas pelo usuário que está sendo chamado
- Saudação de conversão de texto em fala personalizada especificada no usuário que está sendo chamado

O idioma usado para reproduzir as saudações do sistema é, em ordem de prioridade, o idioma de prompt primário e secundário especificado na política de caixa postal online atribuída ao usuário, o idioma preferencial especificado para o usuário ou o idioma do locatário padrão.

A saudação personalizada e de ausência temporária é registrada pelo usuário no idioma escolhido pelo usuário.

Se as saudações personalizadas de conversão de texto em fala forem especificadas para o usuário pelo usuário ou pelo administrador do locatário, o idioma usado para gerar a fala será o PromptLanguage especificado junto com as saudações de conversão de texto em fala.

As saudações personalizadas de conversão de texto em fala só serão usadas se não houver saudações personalizadas registradas para o usuário.

## <a name="transcription"></a>Transcrição
Se habilitado pela política de caixa postal online para o usuário que está sendo chamado, Caixa postal na Nuvem tentará transcrever a caixa postal deixada pelo chamador. Ele usará a detecção de fala para entender o idioma usado no conteúdo de áudio e, se possível, transcrever o conteúdo usando o idioma detectado.

## <a name="transcription-translation"></a>Tradução de transcrição
Se habilitado pela política de caixa postal online para o usuário que está sendo chamado, Caixa postal na Nuvem traduzirá a caixa postal transcrita. Ele traduzirá do idioma detectado durante a detecção de fala para, em ordem de prioridade, o idioma preferencial especificado para o usuário ou o idioma do locatário padrão.

## <a name="voicemail-message-template"></a>Modelo de mensagem de caixa postal
Caixa postal na Nuvem gerará a mensagem de voz usando um modelo de idioma com base em, em ordem de prioridade, o idioma preferencial especificado para o usuário ou o idioma de locatário padrão.

## <a name="setting-the-preferred-language-for-a-user"></a>Definindo o idioma preferencial para um usuário
Você pode definir o idioma preferencial para um usuário usando o PowerShell no Azure Active Directory ou no Active Directory local. Para obter mais informações, [consulte Como definir configurações de idioma e região para o Microsoft 365 ou Office 365](/office365/troubleshoot/access-management/set-language-and-region).

Os usuários podem alterar seu próprio idioma preferido por meio de suas configurações depois de entrar. Para obter mais informações, consulte [Alterar o idioma de exibição e o fuso horário no Microsoft 365 para Empresas](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>Alterar o idioma do sistema para todas as pessoas na organização

1. Entre com sua conta [de administrador global](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).

2. Na página Centro de administração do Microsoft 365, escolha **Configurações da** > **Organização configurações** > **perfil da organização**.

3. Escolha **informações da organização**.

4. Selecione um idioma na lista **Idioma preferencial** para todas as pessoas em sua organização.

5. Escolha **Salvar**.

**Os idiomas disponíveis são determinados pelo local da organização**. Por exemplo, se a sua organização está nos Estados Unidos, você pode definir o idioma padrão como inglês ou espanhol. Se a sua organização está no Canadá, você pode escolher entre inglês e francês.

## <a name="supported-languages-in-cloud-voicemail"></a>Idiomas com suporte no Caixa postal na Nuvem
Para obter uma lista de idiomas com suporte no Caixa postal na Nuvem microsoft Teams e Skype for Business, consulte [Caixa postal na Nuvem idiomas compatíveis](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>Saudação personalizada registrada por um usuário
Os usuários podem gravar suas próprias saudações personalizadas e fora do escritório. Confira [as configurações do cliente da área de](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) trabalho do Teams [e verifique Skype for Business caixa postal e opções](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>Saudação de conversão de texto em fala personalizada especificada para um usuário
O administrador de locatários pode especificar a saudação de texto em fala personalizada e o idioma de prompt para um usuário usando a guia Caixa Postal na página de detalhes do usuário no Centro de administração do Teams ou usando o cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) .

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>Saudação de conversão de texto em fala personalizada especificada por um usuário
Os usuários podem especificar suas próprias saudações personalizadas de conversão de texto em fala e o idioma usado para as saudações. Para o Microsoft Teams – os usuários podem alterar a saudação da caixa postal das [configurações do cliente da área de trabalho do Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). Por Skype for Business - [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) e escolha um novo idioma em **Idioma do Prompt**. 


## <a name="related-articles"></a>Artigos relacionados

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
