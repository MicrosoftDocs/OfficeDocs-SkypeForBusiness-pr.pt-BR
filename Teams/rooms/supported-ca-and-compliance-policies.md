---
title: Políticas de conformidade de dispositivos do Intune e acesso condicional com suporte para Salas do Microsoft Teams
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
description: Saiba mais sobre as políticas de conformidade de dispositivos do Access condicional e do Intune com suporte para Salas do Microsoft Teams.
ms.openlocfilehash: f3b115430779324a260232ce45ba125859abdde8
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689047"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Políticas de conformidade de dispositivos do Intune e acesso condicional com suporte para Salas do Microsoft Teams

Este artigo fornece políticas de conformidade de dispositivos Do Intune e acesso condicional com suporte para Salas do Microsoft Teams. Para ver as práticas recomendadas e as políticas de exemplo, consulte As práticas recomendadas de conformidade do Acesso Condicional e do [Intune para](conditional-access-and-compliance-for-devices.md) Salas do Microsoft Teams.

> [!NOTE]
> Salas do Teams já deve ser implantado nos dispositivos aos que você deseja atribuir políticas de Acesso Condicional. Se você ainda não tiver implantado Salas do Teams, consulte [Criar](with-office-365.md) contas de recursos para salas e dispositivos Teams compartilhados e [Implantar Salas do Microsoft Teams no Android](../devices/collab-bar-deploy.md) para obter mais informações.

## <a name="supported-conditional-access-policies"></a>Políticas de Acesso Condicional com Suporte  

A lista a seguir inclui as políticas de Acesso Condicional com suporte para Salas do Teams no Windows e no Android:

| Atribuição | Windows | Android |
|------------|---------|---------|
| Identidades de usuário ou carga de trabalho |Com suporte | Compatível |
|Aplicativos ou ações na nuvem | Com suporte <br><br> Salas do Teams precisa acessar os três aplicativos cloud a seguir quando estiver Teams modo somente: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams | Com suporte <br><br> Salas do Teams precisa acessar os três aplicativos cloud a seguir quando estiver Teams modo somente: Office 365 Exchange Online, Office 365 SharePoint Online e Microsoft Teams |
|**Condições**| --- | --- |
| Risco do usuário | Com suporte | Compatível |
| Risco de entrar | Com suporte | Compatível |
| Plataformas de dispositivo | Com suporte | Compatível |
| Locais | Com suporte | Compatível |
|Aplicativos cliente |Incompatível| Incompatível |
|Filtrar para dispositivos | Com suporte | Compatível |
|**Grant**| --- | --- |
| Bloquear o acesso | Com suporte | Compatível |
| Conceder acesso | Com suporte | Compatível | 
| Exigir autenticação multifa factor | Incompatível | Incompatível |
| Exigir que o dispositivo seja marcado como compatível | Com suporte | Compatível |
|Exigir dispositivo ingressado no Azure AD híbrido | Incompatível | Incompatível |
|Exigir aplicativo cliente aprovado | Incompatível | Incompatível |
| Exigir política de proteção de aplicativo | Incompatível |Incompatível |
| Exigir alteração de senha | Incompatível | Incompatível |

> [!NOTE]
> Skype for Business Online está aposentado e não tem suporte. Skype for Business aplicativo de nuvem online não é suportado para políticas de Acesso Condicional baseadas em conformidade de dispositivos.

> [!NOTE]
> Salas do Microsoft Teams no Windows devem atender aos seguintes requisitos para dar suporte aos controles de concessão de conformidade do dispositivo:
>
> - Salas do Microsoft Teams aplicativo 4.8.19.0 ou superior
> - Windows 10 versão 20H2 e superior (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Políticas de conformidade de dispositivos com suporte 

Salas do Microsoft Teams no Windows e Salas do Teams no Android suportam políticas de conformidade de dispositivos diferentes.

#### <a name="teams-rooms-on-windows"></a>[Salas do Teams no Windows](#tab/mtr-w)

Abaixo está uma tabela de configurações e recomendações de conformidade do dispositivo para seu uso com Salas do Teams.  

|Política | Disponibilidade | Observações|
|---------|-------------|-------|
| [**Saúde do dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Exigir BitLocker| Com suporte | Use somente se você habilitar o BitLocker pela primeira vez Salas do Teams. |
|Exigir que a inicialização segura seja habilitada no dispositivo |Com suporte |Inicialização Segura é um requisito para Salas do Teams. |
|Exigir integridade de código |Com suporte  | A integridade do código já é um requisito para Salas do Teams. |
| [**Propriedades do dispositivo**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Versão do sistema operacional (mínimo, máximo) |Incompatível | Salas do Teams atualizações automáticas para versões mais recentes do Windows e definir valores aqui podem impedir o logon bem-sucedido após uma atualização do sistema operacional.|
|Versão do sistema operacional para dispositivos móveis (mínimo, máximo) | Sem suporte. | Não disponível |
| Builds de sistema operacional válidos | Incompatível | Não disponível |
| [**Conformidade do Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Exigir conformidade do dispositivo do Configuration Manager | Com suporte |  Não disponível |
| [**Segurança do sistema**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Todas as políticas de senha | Incompatível | As políticas de senha podem impedir que a Skype local entre automaticamente. |
| Exigir criptografia de armazenamento de dados no dispositivo. | Com suporte  | Use somente se você tiver habilitado pela primeira vez a criptografia de armazenamento de dados em Salas do Teams. |
| Firewall | Com suporte | Firewall já é um requisito para Salas do Teams |
| Módulo de plataforma confiável (TPM) | Com suporte | O Trusted Platform Module (TPM) já é um requisito para Salas do Teams. |
| Antivírus | Com suporte | Antivírus (Windows Defender) já é um requisito para Salas do Teams. |
| Antispyware | Com suporte | O antispyware (Windows Defender) já é um requisito para Salas do Teams. |
| Microsoft Defender Antimalware | Com suporte | O Microsoft Defender Antimalware já é um requisito para Salas do Teams. |
| Versão mínima do Microsoft Defender Antimalware | Sem suporte. | Salas do Teams atualiza automaticamente esse componente para que não haja necessidade de definir políticas de conformidade.|
| Inteligência de segurança do Microsoft Defender Antimalware
atualizado | Com suporte | Valide se o Microsoft Defender Antimalware já é um requisito para Salas do Teams. |
| Proteção em tempo real | Com suporte | Proteções em tempo real já são um requisito para Salas do Teams. |
| [**Microsoft Defender para Ponto de Extremidade**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Exigir que o dispositivo seja em ou sob a pontuação de risco do computador. | Com suporte |  Não disponível |

#### <a name="teams-rooms-on-android"></a>[Salas do Teams no Android](#tab/mtr-a)

Abaixo está uma tabela de configurações e recomendações de conformidade do dispositivo para seu uso com Salas do Teams.  

| Política | Disponibilidade | Observações |
|---------|-------------|-------|
| [**Microsoft Defender para Ponto de Extremidade**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Exigir que o dispositivo seja em ou sob a pontuação de risco do computador | Incompatível |  Não disponível |
| [**Saúde do dispositivo**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Dispositivo gerenciado com o administrador de dispositivos | Sem suporte. | Teams dispositivos Android são gerenciados com dispositivo
administrator. |
| Dispositivos com raiz | Com suporte |  Não disponível |
| Exigir que o dispositivo seja em ou sob o nível de ameaça do dispositivo | Incompatível |  Não disponível |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Os Serviços do Google Play estão configurados | Incompatível | O Google play não está instalado em Teams dispositivos Android. |
| Provedor de segurança atualizado | Incompatível | O Google play não está instalado em Teams dispositivos Android. |
| Verificação de ameaças em aplicativos | Incompatível | O Google play não está instalado em Teams dispositivos Android. |
| Atestado de dispositivo SafetyNet | Incompatível | O Google play não está instalado em Teams dispositivos Android.|
| [**Propriedades do dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Versão do sistema operacional (mínimo, máximo) | Com suporte |  Não disponível |
[**Segurança do sistema**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Exigir criptografia de armazenamento de dados no dispositivo. |Com suporte |  Não disponível |
[**Segurança do dispositivo**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquear aplicativos de fontes desconhecidas | Incompatível | Somente Teams administradores instalam aplicativos ou ferramentas OEM |
| Portal da Empresa integridade do tempo de execução do aplicativo | Com suporte |  Não disponível|
| Aplicativos restritos | Incompatível |  Não disponível |
| Bloquear a depuração USB no dispositivo | Com suporte |  Não disponível|
[**Todos os dispositivos Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Máximo de minutos de inatividade antes que a senha seja necessária | Incompatível |  Não disponível |
| Exigir uma senha para desbloquear dispositivos móveis | Incompatível | Não disponível |
| [**Android 10 e posterior**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 e anterior ou Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Tipo de senha necessário |Incompatível | Não disponível|

---
