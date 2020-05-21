---
title: Gerenciar o acesso de convidados no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como criar suas primeiras equipes e canais, pioneiros no início, monitorar o uso e os comentários e obter recursos para planejar a implementação em toda a organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83f4e4cdff4515f89a5b3fe68c91d848f9ae5dda
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326448"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gerenciar o acesso de convidados no Microsoft Teams
======================================

> [!IMPORTANT]
> Talvez seja necessário esperar algumas horas para que as alterações entrem em vigor. 

**Guest** é um tipo de usuário no Microsoft Teams que está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise, do Microsoft 365 Business Basic e do Office 365 Education. Não é necessária nenhuma licença adicional do Office 365. Leia mais sobre o [Licenciamento de acesso de convidado](#guest-access-licensing-limits) abaixo.

O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão. Para obter detalhes sobre como ativar o acesso de convidado, consulte [Ativar ou desativar o acesso de convidado a equipes](set-up-guests.md)ou usar a [lista de verificação de acesso de convidado](guest-access-checklist.md) para orientá-lo na configuração.

Após a ativação do acesso de convidado, você pode definir as configurações para convidados usando os controles descritos em [gerenciar as configurações do teams para sua organização](enable-features-office-365.md) e [gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md).     
    
Os administradores de ti podem adicionar convidados no nível do locatário, definir e gerenciar políticas e permissões do usuário de convidado e receber relatórios sobre atividades do usuário convidado. Esses controles estão disponíveis no centro de administração do teams. O conteúdo e as atividades do usuário convidado se enquadram na mesma proteção de conformidade e auditoria que o restante do Office 365.

Os proprietários da equipe podem convidar novos convidados e adicionar usuários convidados do diretório existente a suas equipes no centro de administração do teams. Identifique os usuários convidados na página **Teams**  >  **Manage Teams** e defina recursos relacionados ao canal para convidados na página de acesso de convidados de **configurações de toda a organização**  >  **Guest access** . As configurações incluem permitir que os convidados criem, atualizem e excluam canais, conforme mostrado na ilustração a seguir.

![Configurações de permissões de convidado no Teams](media/manage-guest-access-image1.png)
  
Você pode usar o portal do Azure Active Directory (Azure AD) para gerenciar convidados e seu acesso aos recursos do Office 365 e do teams. O acesso de convidados do teams usa os recursos de colaboração do Azure AD Business-to-Business (B2B) como a infraestrutura subjacente para armazenar informações sobre os princípios de segurança, como propriedades de identidade, associações e configurações de autenticação multi-fator. Para saber mais sobre o Azure AD B2B, confira [o que é colaboração B2B do Azure ad?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [perguntas frequentes sobre colaboração do Active Directory B2B do Azure](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> O Microsoft Teams sempre honra as configurações externas do Azure AD para permitir ou impedir que os usuários convidados sejam adições ao locatário. Para obter mais detalhes, consulte [autorizar o acesso de convidado no Microsoft Teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Limites de licenciamento de acesso de convidado

O Teams não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário é baseado no que o licenciamento do seu Azure AD permite - normalmente, 5 convidados por usuário licenciado. Para obter mais informações, confira [Licenciamento de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

Devido a essas limitações de licenciamento (e para manter seu locatário atualizado), você deve revisar o acesso de convidado periodicamente para identificar os usuários que têm acesso a que eles não precisam mais. Você pode usar o Azure AD para criar uma revisão do Access para os membros do grupo ou usuários atribuídos a um aplicativo. Criar análises recorrentes do Access pode poupar tempo. Se precisar revisar rotineiramente os usuários que têm acesso a um aplicativo ou membros de um grupo, você pode definir a frequência dessas análises. 

Você também pode fazer uma crítica de acesso de convidado, pedir aos convidados que examinem sua própria associação ou peça ao proprietário do aplicativo ou ao responsável por decisões comerciais para executar a revisão do Access. Use o portal do Azure para executar análises de acesso de convidado. Para obter mais informações, consulte [gerenciar o acesso de convidados com as críticas do Azure ad Access](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Pré-requisitos para análises do Azure AD Access

As avaliações do Access estão disponíveis com a versão Premium P2 do Azure AD, que está incluída no Microsoft Enterprise Mobility + Security, e5. Para obter mais informações, consulte [edições do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Cada usuário que interage com esse recurso criando uma revisão, preenchendo uma revisão ou confirmando o acesso dela deve ter uma licença.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Tempo de retardo para as configurações de acesso de convidado entrarem em vigor

Para as configurações de acesso de convidado no Azure Active Directory, demora algumas horas para que as alterações entrem em vigor no Microsoft 365 ou no Office 365. Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o recurso convidado não esteja ativado ou que as configurações ainda não sejam efetivadas. Para obter ajuda com problemas para configurar o acesso de convidado, leia [solucionar problemas de acesso de convidado no Teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Acesso externo (federação) e o acesso de convidado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Mais informações

Para obter informações sobre como usar o PowerShell para gerenciar o acesso de convidados, consulte [usar o PowerShell para controlar o acesso de convidados a uma equipe](guest-access-powershell.md).


