---
title: Práticas recomendadas de autenticação para Microsoft Teams gerenciamento de dispositivos compartilhados de dispositivos Android.
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Práticas recomendadas no gerenciamento de dispositivos Android compartilhados Teams. Isso apresenta Acesso Condicional, política de senha, consultoria de autenticação multifacional e muito mais.
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279229"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Práticas recomendadas de autenticação para Teams gerenciamento de dispositivos compartilhados em dispositivos Android

Os objetivos dos dispositivos usados com Teams fazem diferentes estratégias de gerenciamento de dispositivos necessárias. Por exemplo, um tablet de negócios pessoal usado por um único vendedor tem um conjunto diferente de necessidades de um telefone de chamada compartilhado por muitas pessoas do serviço de atendimento ao cliente.

Os administradores de segurança e as equipes de operações devem planejar os dispositivos que podem ser usados na organização. Eles devem implementar *medidas de* segurança mais adequadas para cada finalidade. As recomendações deste artigo facilitam algumas dessas decisões.

>[!NOTE]
>O Acesso Condicional requer uma assinatura Azure Active Directory (Azure AD) Premium assinatura.

>[!NOTE]
>As políticas para dispositivos móveis Android podem não se aplicar Teams dispositivos Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>As recomendações de autenticação são diferentes para dispositivos Android pessoais versus compartilhados

Os Teams dispositivos compartilhados não podem usar os mesmos requisitos para registro e conformidade usados em dispositivos pessoais. A aplicação de requisitos de autenticação de dispositivo pessoal a dispositivos compartilhados causará problemas de entrada.

1.  **Os dispositivos são assinados devido a políticas de senha.**

Contas usadas em Teams dispositivos têm uma política de expiração de senha. As contas usadas com dispositivos compartilhados não têm um usuário específico para atualizá-las e restaurá-las para um estado de trabalho quando suas senhas expirarem. Se sua organização exigir que as senhas expirem e redefinirem ocasionalmente, essas contas deixarão de funcionar em Teams dispositivos até que um administrador Teams redefina a senha e entre novamente.

**Desafio**: quando se trata de acessar. Teams de um dispositivo, a conta de uma pessoa tem uma política de expiração de senha. Quando a senha vai expirar, eles simplesmente a alteram. Mas contas usadas *em dispositivos* compartilhados (contas de recursos) podem não estar conectadas a uma única pessoa que pode alterar uma senha conforme necessário. Isso significa que uma senha pode expirar e deixar os funcionários no local, sem saber como retomar seu trabalho.

Quando sua organização exigir uma redefinição de senha ou impor a expiração da senha, certifique-se de que um administrador Teams esteja preparado para redefinir a senha para que essas contas compartilhadas possam entrar novamente.

2.  **Os dispositivos não conseguem entrar devido a políticas de acesso condicional.**

**Desafio**: Os dispositivos compartilhados não podem estar em conformidade com as políticas de Acesso Condicional do Azure AD para contas de usuário ou dispositivos pessoais. Se os dispositivos compartilhados são agrupados com contas de usuário ou dispositivos pessoais para uma política de Acesso Condicional, a entrada *falhará*.

Por exemplo, se a autenticação multifa factor for necessária para acessar Teams, a entrada do usuário de um código será necessária para concluir essa autenticação. Os dispositivos compartilhados geralmente não têm um único usuário que pode configurar e concluir a autenticação multifaionária. Além disso, se a conta precisar reauthenticar a cada dias X, um dispositivo compartilhado não poderá resolver o desafio sem a intervenção de um usuário.

A autenticação multifafação não é suportada com dispositivos compartilhados. Os métodos a usar em vez disso são descritos abaixo.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Práticas recomendadas para a implantação de dispositivos android compartilhados com Teams

A Microsoft recomenda as configurações a seguir ao implantar Teams dispositivos em sua organização.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usar uma conta de recurso e reduzir sua expiração de senha**

Teams dispositivos compartilhados devem usar uma caixa [de correio Exchange recurso.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) Criar essas caixas de correio gera uma conta automaticamente. Essas contas podem ser sincronizadas com o Azure AD do Active Directory ou criadas diretamente no Azure AD. Quaisquer políticas de expiração de senha para usuários também se aplicarão a contas usadas em Teams dispositivos compartilhados, portanto, para evitar interrupções causadas por políticas de expiração de senha, de definir a política de expiração de senha para que dispositivos compartilhados nunca expirem.

A partir de Teams dispositivos CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versão 1449/1.0.94.2021022403 para telefones Teams) e [CY2021 Atualização #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versão 1449/1.0.96.2021051904 para Salas do Microsoft Teams android), os administradores de locatários podem entrar em dispositivos Teams remotamente. Em vez de compartilhar senhas com técnicos para configurar dispositivos, os administradores de locatários devem usar a entrada remota para emitir códigos de verificação. A entrada pode ser feita para esses dispositivos Teams centro de administração.

Para obter mais informações, consulte [Provisionamento remoto e entrar Teams dispositivos Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Revisar essas políticas de Acesso Condicional**

O Acesso Condicional do Azure AD define requisitos adicionais que os dispositivos devem atender para entrar. Para Teams dispositivos, revise as diretrizes a seguir para determinar se você foi o autor das políticas que permitirão que os usuários de dispositivo compartilhados trabalhem.

> [!TIP]
> Para uma visão geral do Acesso Condicional, consulte [O que é o Acesso Condicional](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>Não use a autenticação multifafação para dispositivos compartilhados

Contas para dispositivos compartilhados são vinculadas a uma sala ou espaço físico, em vez de a uma conta de usuário final. Como os dispositivos compartilhados não suportam a autenticação multifagão, exclua dispositivos compartilhados de qualquer política de autenticação multifagão.

>[!TIP]
>Use local [nomeado ou](/azure/active-directory/conditional-access/location-condition) [exigir dispositivo compatível para](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) proteger dispositivos compartilhados.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Você pode usar o acesso baseado em local com locais nomeados

Se dispositivos compartilhados são provisionados em um local bem definido que pode ser identificado com um intervalo de endereços IP, você pode configurar o Acesso [](/azure/active-directory/conditional-access/location-condition) Condicional usando locais nomeados para esses dispositivos. Essa condição permitirá que esses dispositivos acessem seus recursos corporativos somente quando eles estão em sua rede.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Quando e quando não exigir dispositivos compartilhados compatíveis

>[!NOTE]
>A conformidade do dispositivo requer uma licença do Intune.

Se você estiver registrando dispositivos compartilhados no Intune, poderá configurar a conformidade do dispositivo como um controle no Acesso Condicional para que somente dispositivos compatíveis possam acessar seus recursos corporativos. Teams dispositivos podem ser configurados para políticas de Acesso Condicional com base na conformidade do dispositivo. Para obter mais informações, consulte [Acesso Condicional: Exigir dispositivo ingressado no Azure AD híbrido ou compatível](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Para definir a configuração de conformidade para seus dispositivos usando o Intune, consulte Usar políticas de conformidade para definir regras para dispositivos [que você gerencia com o Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Dispositivos compartilhados que estão sendo usados *para o hot desking* devem ser excluídos das políticas de conformidade. As polícias de conformidade impedem que os dispositivos se inscrevam na conta de usuário do hot desk. **Em vez disso, use locais nomeados para proteger esses dispositivos**.
> Para aumentar a segurança, você também pode exigir autenticação [multifafação](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para usuários *de hot desk/* contas de usuário, além das políticas de local nomeadas.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Excluir dispositivos compartilhados das condições de frequência de entrada

No Acesso Condicional, você pode configurar [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) a frequência de entrada para exigir que os usuários entrem novamente para acessar um recurso após um período de tempo especificado. Se a frequência de entrada for imposta para contas de sala, os dispositivos compartilhados sairão até que eles sejam conectados novamente por um administrador. A Microsoft recomenda excluir dispositivos compartilhados de todas as políticas de frequência de entrada.

### <a name="using-filters-for-devices"></a>Usando filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) é um recurso no Acesso Condicional que permite configurar políticas mais granulares para dispositivos com base nas propriedades de dispositivo disponíveis no Azure AD. Você também pode usar seus próprios valores personalizados definindo atributos de extensão de 1 a 15 no objeto de dispositivo e, em seguida, usando-os.

Use filtros para dispositivos para identificar seus dispositivos de área comum e habilitar políticas em dois cenários principais:

1.  Excluindo dispositivos compartilhados de políticas aplicadas a dispositivos pessoais. Por exemplo, exigir a conformidade  do dispositivo não é imposto para dispositivos compartilhados usados para hot desking, mas é *imposto* para todos os outros dispositivos, com base no número do modelo.

2.  Impor políticas especiais em dispositivos compartilhados *que não devem* ser aplicados a dispositivos pessoais. Por exemplo, exigir locais nomeados como política somente para dispositivos de área comum com base em um atributo de extensão que você definiu para esses dispositivos (por exemplo: "CommonAreaPhone").

>[!NOTE] 
> Alguns atributos, como **modelo**, **fabricante** e **operatingSystemVersion** , só podem ser definidos quando os dispositivos são gerenciados pelo Intune. Se seus dispositivos não são gerenciados pelo Intune, use atributos de extensão.
