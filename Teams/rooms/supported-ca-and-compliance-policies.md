---
title: Acesso condicional e políticas de conformidade do Intune suporte para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Saiba mais sobre o acesso condicional e as políticas de conformidade do Intune recomendadas para Salas do Microsoft Teams.
ms.openlocfilehash: 19e4593a6135c79eb156a1b34847ab518d6e8ea4
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059232"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Acesso condicional e políticas de conformidade do Intune suporte para Salas do Microsoft Teams

Este artigo fornece acesso condicional e políticas de conformidade Intune dispositivo com suporte para Salas do Microsoft Teams. Para obter práticas recomendadas e políticas de exemplo, consulte o Acesso Condicional [e Intune práticas recomendadas de conformidade para Salas do Microsoft Teams](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Salas do Teams já deve ser implantado nos dispositivos aos quais você deseja atribuir políticas de Acesso Condicional. Se você ainda não implantou Salas do Teams, consulte Criar contas de recursos [](with-office-365.md) para salas e dispositivos Teams compartilhados e Implantar Salas do Microsoft Teams [no Android](../devices/collab-bar-deploy.md) para obter mais informações.

## <a name="supported-conditional-access-policies"></a>Políticas de acesso condicional com suporte  

A lista a seguir inclui as políticas de Acesso Condicional com suporte para Salas do Teams no Windows e no Android. 

> [!NOTE]
> As políticas do Android com suporte se aplicam a todos os dispositivos Android em espaços compartilhados, incluindo Salas do Teams em Andourd, telefones de área comuns e painéis.

| Atribuição | Windows | Android |
|------------|---------|---------|
| Identidades de usuário ou carga de trabalho |Com suporte | Compatível |
|Ações ou aplicativos de nuvem | Com suporte <br><br> Salas do Teams precisa acessar os três aplicativos de nuvem a seguir quando estiver Teams modo somente: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams | Com suporte <br><br> Salas do Teams precisa acessar os três aplicativos de nuvem a seguir quando estiver Teams modo somente: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams |
|**Condições**| --- | --- |
| Risco do usuário | Com suporte | Compatível |
| Risco de entrada | Com suporte | Compatível |
| Plataformas de dispositivo | Com suporte | Compatível |
| Locais | Com suporte | Compatível |
|Aplicativos cliente |Incompatível| Incompatível |
|Filtrar dispositivos | Com suporte | Compatível |
|**Grant**| --- | --- |
| Bloquear acesso | Com suporte | Compatível |
| Conceder acesso | Com suporte | Compatível | 
| Exigir autenticação multifator | Incompatível | Incompatível |
| Exigir que o dispositivo seja marcado como compatível | Com suporte | Compatível |
|Exigir dispositivo ingressado no Azure AD híbrido | Incompatível | Incompatível |
|Exigir aplicativo cliente aprovado | Incompatível | Incompatível |
| Exigir política de proteção de aplicativo | Incompatível |Incompatível |
| Exigir alteração de senha | Incompatível | Incompatível |

> [!NOTE]
> Skype for Business Online está desativado e não tem suporte. Skype for Business de nuvem online não tem suporte para políticas de Acesso Condicional baseadas em conformidade do dispositivo.

> [!NOTE]
> Salas do Microsoft Teams no Windows devem atender aos seguintes requisitos para dar suporte a controles de concessão de conformidade do dispositivo:
>
> - Salas do Microsoft Teams aplicativo 4.8.19.0 ou superior
> - Windows 10 versão 20H2 e posterior (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Políticas de conformidade de dispositivo com suporte 

Salas do Microsoft Teams no Windows e Salas do Teams no Android dão suporte a diferentes políticas de conformidade do dispositivo.

#### <a name="teams-rooms-on-windows"></a>[Salas do Teams no Windows](#tab/mtr-w)

Abaixo está uma tabela de configurações e recomendações de conformidade do dispositivo para seu uso com Salas do Teams.  

|Política | Disponibilidade | Observações|
|---------|-------------|-------|
| [**Integridade do dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Exigir BitLocker| Com suporte | Use somente se você tiver habilitado o BitLocker pela primeira vez Salas do Teams. |
|Exigir que a Inicialização Segura esteja habilitada no dispositivo |Com suporte |A Inicialização Segura é um requisito para Salas do Teams. |
|Exigir integridade de código |Com suporte  | A integridade do código já é um requisito para Salas do Teams. |
| [**Propriedades do dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versão do sistema operacional (mínimo, máximo) |Incompatível | Salas do Teams atualizações automáticas para versões mais recentes do Windows e definir valores aqui pode impedir a entrada bem-sucedida após uma atualização do sistema operacional.|
|Versão do sistema operacional para dispositivos móveis (mínimo, máximo) | Sem suporte. | Não disponível |
| Compilações válidas do sistema operacional | Incompatível | Não disponível |
| [**Configuration Manager conformidade**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Exigir a conformidade do dispositivo Configuration Manager | Com suporte |  Não disponível |
| [**Segurança do sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Todas as políticas de senha | Incompatível | As políticas de senha podem impedir que a Skype local entre automaticamente. |
| Exigir criptografia de armazenamento de dados no dispositivo. | Com suporte  | Use somente se você tiver habilitado primeiro a criptografia do armazenamento de dados Salas do Teams. |
| Firewall | Com suporte | O firewall já é um requisito para Salas do Teams |
| Trusted Platform Module (TPM) | Com suporte | O TPM (Trusted Platform Module) já é um requisito para Salas do Teams. |
| Antivírus | Com suporte | Antivírus (Windows Defender) já é um requisito para Salas do Teams. |
| Antispyware | Com suporte | O antispyware (Windows Defender) já é um requisito para Salas do Teams. |
| Microsoft Defender Antimalware | Com suporte | O Microsoft Defender Antimalware já é um requisito para Salas do Teams. |
| Versão mínima do Microsoft Defender Antimalware | Sem suporte. | Salas do Teams atualiza automaticamente esse componente para que não haja necessidade de definir políticas de conformidade.|
| Inteligência de segurança do Microsoft Defender Antimalware
atualizado | Com suporte | Valide se o Microsoft Defender Antimalware já é um requisito para Salas do Teams. |
| Proteção em tempo real | Com suporte | As proteções em tempo real já são um requisito para Salas do Teams. |
| [**Microsoft Defender para Ponto de Extremidade**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo. | Com suporte |  Não disponível |

#### <a name="teams-rooms-on-android"></a>[Salas do Teams no Android](#tab/mtr-a)

Abaixo está uma tabela de configurações e recomendações de conformidade do dispositivo para seu uso com Salas do Teams.  

| Política | Disponibilidade | Observações |
|---------|-------------|-------|
| [**Microsoft Defender para Ponto de Extremidade**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Exigir que o dispositivo esteja em ou abaixo da pontuação de risco do computador | Incompatível |  Não disponível |
| [**Integridade do dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo gerenciado com o administrador do dispositivo | Obrigatório | Teams gerenciamento de dispositivos Android exige que o administrador do dispositivo esteja habilitado. |
| Dispositivos com raiz | Com suporte |  Não disponível |
| Exigir que o dispositivo esteja no nível de ameaça do dispositivo ou abaixo | Incompatível |  Não disponível |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| O Google Play Services está configurado | Incompatível | O Google Play não está instalado em dispositivos Teams Android. |
| Provedor de segurança atualizado | Incompatível | O Google Play não está instalado em dispositivos Teams Android. |
| Verificação de ameaças em aplicativos | Incompatível | O Google Play não está instalado em dispositivos Teams Android. |
| Atestado de dispositivo SafetyNet | Incompatível | O Google Play não está instalado em dispositivos Teams Android.|
| [**Propriedades do dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versão do sistema operacional (mínimo, máximo) | Com suporte |  Não disponível |
[**Segurança do sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Exigir criptografia de armazenamento de dados no dispositivo. |Com suporte |  Não disponível |
[**Segurança do dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquear aplicativos de fontes desconhecidas | Incompatível | Somente Teams administradores instalam aplicativos ou ferramentas OEM |
| Portal da Empresa de runtime do aplicativo | Com suporte |  Não disponível|
| Aplicativos restritos | Incompatível |  Não disponível |
| Bloquear a depuração USB no dispositivo | Com suporte |  Não disponível|
[**Todos os dispositivos Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Máximo de minutos de inatividade antes que a senha seja necessária | Incompatível |  Não disponível |
| Exigir uma senha para desbloquear dispositivos móveis | Incompatível | Não disponível |
| [**Android 10 e posterior**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 e anterior ou Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo de senha necessário |Incompatível | Não disponível|

---
