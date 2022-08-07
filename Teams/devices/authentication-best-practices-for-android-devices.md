---
title: Práticas recomendadas de autenticação para o gerenciamento de dispositivo compartilhado do Microsoft Teams de dispositivos Android.
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Práticas recomendadas sobre o gerenciamento compartilhado de dispositivos Android no Teams. Isso apresenta Acesso Condicional, política de senha, conselhos de autenticação multifator e muito mais.
ms.collection:
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0f658a70235440563d7cb3910830c56923b60f3e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270096"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Práticas recomendadas de autenticação para o gerenciamento de dispositivo compartilhado do Teams em dispositivos Android

As metas dos dispositivos usados com o Teams tornam diferentes estratégias de gerenciamento de dispositivos necessárias. Por exemplo, um tablet comercial pessoal usado por um único vendedor tem um conjunto diferente de necessidades de um telefone de chamada compartilhado por muitas pessoas do serviço de atendimento ao cliente.

Os administradores de segurança e as equipes de operações devem planejar os dispositivos que podem ser usados na organização. Eles devem implementar *medidas de* segurança mais adequadas para cada finalidade. As recomendações deste artigo facilitam algumas dessas decisões.

>[!NOTE]
>O Acesso Condicional requer uma assinatura Premium do Azure Active Directory (Azure AD).

>[!NOTE]
>As políticas para dispositivos móveis Android podem não se aplicar a dispositivos Android do Teams.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>As recomendações de autenticação são diferentes para dispositivos Android pessoais versus compartilhados

Os dispositivos compartilhados do Teams não podem usar os mesmos requisitos de registro e conformidade usados em dispositivos pessoais. Aplicar requisitos de autenticação de dispositivo pessoal a dispositivos compartilhados causará problemas de entrada.

1.  **Os dispositivos são conectados devido a políticas de senha.**

As contas usadas em dispositivos do Teams têm uma política de expiração de senha. As contas usadas com dispositivos compartilhados não têm um usuário específico para atualizá-las e restaurá-las para um estado de trabalho quando suas senhas expirarem. Se sua organização exigir que as senhas expirem e redefinam ocasionalmente, essas contas deixarão de funcionar em dispositivos do Teams até que um administrador do Teams redefina a senha e entre novamente.

**Desafio**: quando se trata de acesso. As equipes de um dispositivo, a conta de uma pessoa tem uma política de expiração de senha. Quando a senha vai expirar, eles simplesmente a alteram. Mas as contas usadas *em dispositivos compartilhados* (contas de recursos) podem não estar conectadas a uma única pessoa que possa alterar uma senha conforme necessário. Isso significa que uma senha pode expirar e deixar os trabalhadores no local, sem saber como retomar seu trabalho.

Quando sua organização exigir uma redefinição de senha ou impor a expiração de senha, verifique se um administrador do Teams está preparado para redefinir a senha para que essas contas compartilhadas possam entrar novamente.

2.  **Os dispositivos não podem entrar devido a políticas de acesso condicional.**

**Desafio**: os dispositivos compartilhados não podem estar em conformidade Azure AD políticas de Acesso Condicional para contas de usuário ou dispositivos pessoais. Se os dispositivos compartilhados forem agrupados com contas de usuário ou dispositivos pessoais para uma política de Acesso Condicional, a entrada *falhará*.

Por exemplo, se a autenticação multifator for necessária para acessar o Teams, a entrada do usuário de um código será necessária para concluir essa autenticação. Os dispositivos compartilhados geralmente não têm um único usuário que possa configurar e concluir a autenticação multifator. Além disso, se a conta precisar ser autenticada novamente a cada X dias, um dispositivo compartilhado não poderá resolver o desafio sem a intervenção de um usuário.

A autenticação multifator não é compatível com dispositivos compartilhados. Os métodos a serem usados são descritos abaixo.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Práticas recomendadas para a implantação de dispositivos Android compartilhados com o Teams

A Microsoft recomenda as seguintes configurações ao implantar dispositivos do Teams em sua organização.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usar uma conta de recurso e limitar sua expiração de senha**

Os dispositivos compartilhados do Teams devem usar uma caixa [de correio de recurso do Exchange](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). Criar essas caixas de correio gera uma conta automaticamente. Essas contas podem ser sincronizadas com Azure AD do Active Directory ou criadas diretamente no Azure AD. Todas as políticas de expiração de senha para usuários também serão aplicadas a contas usadas em dispositivos compartilhados do Teams, portanto, para evitar interrupções causadas por políticas de expiração de senha, defina a política de expiração de senha para que os dispositivos compartilhados nunca expirem.

A partir dos dispositivos teams CY21 [Atualização nº 1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versão 1449/1.0.94.2021022403 para telefones Teams) e [CY2021 Atualização nº 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versão 1449/1.0.96.2021051904 para Salas do Microsoft Teams no Android), os administradores de locatários podem entrar em dispositivos do Teams remotamente. Em vez de compartilhar senhas com técnicos para configurar dispositivos, os administradores de locatários devem usar a entrada remota para emitir códigos de verificação. A entrada pode ser feita para esses dispositivos no centro de administração do Teams.

Para obter mais informações, consulte [Provisionamento remoto e entrar em dispositivos Android do Teams](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Examinar essas políticas de Acesso Condicional**

Azure AD acesso condicional define requisitos adicionais que os dispositivos devem atender para entrar. Para dispositivos do Teams, examine as diretrizes a seguir para determinar se você criou as políticas que permitirão que os usuários de dispositivos compartilhados executem seu trabalho.

> [!TIP]
> Para obter uma visão geral do Acesso Condicional, consulte [O que é Acesso Condicional](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Não usar a autenticação multifator para dispositivos compartilhados

As contas de dispositivos compartilhados são vinculadas a uma sala ou espaço físico, em vez de a uma conta de usuário final. Como os dispositivos compartilhados não dão suporte à autenticação multifator, exclua dispositivos compartilhados de nenhuma política de autenticação multifator.

>[!TIP]
>Use o [local nomeado ou](/azure/active-directory/conditional-access/location-condition) [exija dispositivo compatível para](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) proteger dispositivos compartilhados.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Você pode usar o acesso baseado em localização com locais nomeados

Se os dispositivos compartilhados forem provisionados em um local bem definido que possa ser identificado com um intervalo de endereços IP, você poderá configurar o [](/azure/active-directory/conditional-access/location-condition) Acesso Condicional usando locais nomeados para esses dispositivos. Essa condicional permitirá que esses dispositivos acessem seus recursos corporativos somente quando eles estiverem em sua rede.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quando e quando não exigir dispositivos compartilhados em conformidade

>[!NOTE]
>A conformidade do dispositivo requer Intune licença.

Se você estiver registrando dispositivos compartilhados no Intune, poderá configurar a conformidade do dispositivo como um controle no Acesso Condicional para que somente dispositivos compatíveis possam acessar seus recursos corporativos. Os dispositivos do Teams podem ser configurados para políticas de Acesso Condicional com base na conformidade do dispositivo. Para obter mais informações, consulte [Acesso Condicional: Exigir dispositivos Azure AD ingressados em conformidade ou híbrido.](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)

Para definir a configuração de conformidade para seus dispositivos usando Intune, consulte Usar políticas de conformidade para definir regras para dispositivos gerenciados [com Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Os dispositivos compartilhados que estão sendo usados *para o hot desking* devem ser excluídos das políticas de conformidade. As políticas de conformidade impedem que os dispositivos se registrem na conta de usuário do hot desk. **Em vez disso, use locais nomeados para proteger esses dispositivos**.
> Para aumentar a segurança, você também pode exigir [a autenticação multifator](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para usuários/contas de usuário do *hot desking* , além das políticas de localização nomeadas.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Excluir dispositivos compartilhados das condições de frequência de entrada

No Acesso Condicional, você pode configurar [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) a frequência de entrada para exigir que os usuários se conectem novamente para acessar um recurso após um período de tempo especificado. Se a frequência de entrada for imposta para contas de sala, os dispositivos compartilhados sairão até que sejam conectados novamente por um administrador. A Microsoft recomenda excluir dispositivos compartilhados de qualquer política de frequência de entrada.

### <a name="using-filters-for-devices"></a>Usando filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) é um recurso no Acesso Condicional que permite configurar políticas mais granulares para dispositivos com base nas propriedades do dispositivo disponíveis no Azure AD. Você também pode usar seus próprios valores personalizados definindo atributos de extensão de 1 a 15 no objeto de dispositivo e, em seguida, usando-os.

Use filtros para dispositivos para identificar seus dispositivos de área comum e habilitar políticas em dois cenários principais:

1.  Excluindo dispositivos compartilhados de políticas aplicadas a dispositivos pessoais. Por exemplo, exigir a conformidade  do dispositivo não é imposto para dispositivos compartilhados usados para mesas dinâmicas, mas é imposto para todos os outros dispositivos, com base no número do modelo.

2.  Impor políticas especiais em dispositivos compartilhados *que não devem* ser aplicados a dispositivos pessoais. Por exemplo, exigir locais nomeados como política somente para dispositivos de área comum com base em um atributo de extensão definido para esses dispositivos (por exemplo: "CommonAreaPhone").

>[!NOTE] 
> Alguns atributos, como **modelo**, **fabricante** e **operatingSystemVersion**, só podem ser definidos quando os dispositivos são gerenciados por Intune. Se os dispositivos não forem gerenciados por Intune, use atributos de extensão.
