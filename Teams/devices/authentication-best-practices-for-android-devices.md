---
title: Práticas recomendadas de autenticação para dispositivos Android
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Um guia de práticas recomendadas para a autenticação Teams dispositivos Android.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576161"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Práticas recomendadas de autenticação para Teams dispositivos Android

Este artigo fornece diretrizes gerais e práticas recomendadas para implantar políticas de autenticação para Teams telefones e dispositivos de chamada.

>[!NOTE]
>O Acesso Condicional requer uma assinatura Azure Active Directory (Azure AD) Premium assinatura.

>[!NOTE]
>As políticas para dispositivos móveis Android podem não se aplicar Teams dispositivos Android.


## <a name="personal-and-shared-devices"></a>Dispositivos pessoais e compartilhados

Dispositivos Teams compartilhados, como dispositivos de sala de reunião ou telefones de área comum, não podem usar os mesmos requisitos para registro e conformidade que normalmente são aplicados a dispositivos pessoais. A aplicação de requisitos de autenticação de dispositivo pessoal a dispositivos compartilhados causará os seguintes problemas de entrada:

1.  **Os dispositivos são assinados devido a políticas de senha**

Contas usadas em Teams dispositivos têm uma política de expiração de senha. Ao contrário dos usuários, as contas usadas com dispositivos compartilhados não têm um usuário designado para atualizá-los e restaurá-los para um estado válido quando suas senhas expirarem. Se sua organização exigir que as senhas expirem e redefinirem periodicamente, essas contas deixarão de funcionar em Teams dispositivos até que um administrador Teams redefina a senha e entre novamente.

2.  **Dispositivos não conseguem entrar devido a políticas de acesso condicional**

Os dispositivos compartilhados não podem estar em conformidade com as políticas de Acesso Condicional do Azure AD para contas de usuário ou dispositivos pessoais. Se os dispositivos compartilhados são agrupados com contas de usuário ou dispositivos pessoais para uma política de Acesso Condicional, a entrada falhará.

Por exemplo, se a autenticação multifa factor for necessária para acessar Teams, a intervenção do usuário será necessária para concluir a autenticação. Os dispositivos compartilhados não suportam a autenticação multifagássion. Da mesma forma, se a conta estiver configurada para reauthenticar a cada X dias, um dispositivo compartilhado não poderá resolver o desafio sem intervenção do usuário.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Práticas recomendadas para implantações Teams de dispositivos compartilhados

A Microsoft recomenda as configurações a seguir ao implantar Teams dispositivos em sua organização.

### <a name="password-policy"></a>**Política de senha**

Teams dispositivos compartilhados devem usar uma [conta Exchange recurso](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). Essas contas podem ser sincronizadas do Active Directory ou criadas diretamente no Azure AD. Todas as políticas de expiração de senha para usuários também se aplicam a contas usadas Teams dispositivos compartilhados também.

Para evitar interrupções causadas por políticas de expiração de senha, de definir a política de expiração de senha para que dispositivos compartilhados nunca expirem.

A partir dos dispositivos Teams CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versão 1449/1.0.94.2021022403 para telefones Teams) e [CY2021 Atualização #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versão 1449/1.0.96.2021051904 para Salas do Microsoft Teams no Android), os administradores de locatários podem entrar Teams dispositivos remotamente. Não compartilhe senhas com técnicos para configurar dispositivos. Um administrador, use a entrada remota para emitir códigos de verificação e, em seguida, entre nesses dispositivos Teams centro de administração.

Para obter mais informações, consulte [Provisionamento remoto e entrar Teams dispositivos Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="conditional-access-policies"></a>**Políticas de Acesso Condicional**

O Acesso Condicional do Azure AD define requisitos adicionais que os dispositivos devem atender para entrar. Para Teams dispositivos, revise as seguintes diretrizes para determinar se você foi o autor das políticas apropriadas. Para uma visão geral do Acesso Condicional, consulte [O que é Acesso Condicional](/azure/active-directory/conditional-access/overview).

### <a name="multi-factor-authentication"></a>Autenticação multifator

Contas para dispositivos compartilhados são vinculadas a uma sala ou espaço físico, em vez de a uma conta de usuário. Como os dispositivos compartilhados não suportam a autenticação multifagão, exclua dispositivos compartilhados de qualquer política de autenticação multifagão.

>[!TIP]
>Use local [nomeado ou](/azure/active-directory/conditional-access/location-condition) exigir [dispositivo compatível para](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) proteger dispositivos compartilhados.

### <a name="location-based-access-with-named-locations"></a>Acesso baseado em local com locais nomeados

Se dispositivos compartilhados são provisionados em um local bem definido que pode ser identificado [](/azure/active-directory/conditional-access/location-condition) com um intervalo de endereços IP, você pode configurar o Acesso Condicional usando locais nomeados para esses dispositivos. Essa condição permitirá que esses dispositivos acessem seus recursos corporativos somente quando eles estão em sua rede.

### <a name="require-compliant-device"></a>Exigir dispositivo compatível

>[!NOTE]
>A conformidade do dispositivo requer uma licença do Intune.

Se você estiver registrando dispositivos compartilhados no Intune, poderá configurar a conformidade do dispositivo como um controle no Acesso Condicional para que somente dispositivos compatíveis possam acessar seus recursos corporativos. Teams dispositivos podem ser configurados para políticas de Acesso Condicional com base na conformidade do dispositivo. Para obter mais informações, consulte Acesso Condicional: Exigir dispositivo ingressado no [Azure AD híbrido ou compatível.](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)

Para definir a configuração de conformidade para seus dispositivos usando o Intune, consulte Usar políticas de conformidade para definir regras para dispositivos que você [gerencia com o Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Dispositivos compartilhados que estão sendo usados para hotdesking devem ser excluídos das políticas de conformidade. As polícias de conformidade impedem que os dispositivos se inscrevam na conta de usuário do hot-desk. Em vez disso, use locais nomeados para proteger esses dispositivos.
> Para aumentar a segurança, você também pode exigir autenticação [multifafação](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para usuários de hot-desking, além das políticas nomeadas.

### <a name="sign-in-frequency"></a>Frequência de login

No Acesso Condicional, [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) você pode configurar a frequência de entrada para exigir que os usuários entrem novamente para acessar um recurso após um período de tempo especificado. Se a frequência de entrada for imposta para contas de sala, os dispositivos compartilhados sairão até que eles sejam conectados novamente por um administrador. A Microsoft recomenda excluir dispositivos compartilhados de todas as políticas de frequência de entrada.

### <a name="filters-for-devices"></a>Filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) é um recurso no Acesso Condicional que permite configurar políticas mais granulares para dispositivos com base nas propriedades de dispositivo disponíveis no Azure AD. Você também pode usar seus próprios valores personalizados definindo atributos de extensão de 1 a 15 no objeto de dispositivo e, em seguida, usando-os.

Use filtros para dispositivos para identificar seus dispositivos de área comum e habilitar políticas em dois cenários principais:

1.  Excluindo dispositivos compartilhados de políticas aplicadas a dispositivos pessoais. Por exemplo, exigir a conformidade do dispositivo não é imposto para dispositivos compartilhados usados para hot-desking, mas é imposto para todos os outros dispositivos com base no número do modelo.

2.  Impor políticas especiais em dispositivos compartilhados que não devem ser aplicados a dispositivos pessoais. Por exemplo, exigir locais nomeados como política somente para dispositivos de área comum com base em um atributo de extensão que você definiu para esses dispositivos (por exemplo: "CommonAreaPhone").

>[!NOTE] 
> Alguns atributos, como **modelo,** **fabricante** e **operatingSystemVersion,** só podem ser definidos quando os dispositivos são gerenciados pelo Intune. Se seus dispositivos não são gerenciados pelo Intune, use atributos de extensão.