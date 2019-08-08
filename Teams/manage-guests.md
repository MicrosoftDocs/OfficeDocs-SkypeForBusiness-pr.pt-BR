---
title: Gerenciar o acesso de convidados no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3ede35352436074cbf7c94fc9df78100a73a017
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241806"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gerenciar o acesso de convidados no Microsoft Teams
======================================

**Guest** é um tipo de usuário/licença do Microsoft Teams incluído em todas as assinaturas do Office 365 Business Premium, do Office 365 Enterprise e do Office 365 Education. Não é necessária nenhuma licença adicional do Office 365. O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão. Para obter detalhes sobre como habilitar o acesso de convidado, consulte [Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md).

Após a ativação do tipo de usuário/licença de **convidado** , você pode definir configurações para convidados por meio dos controles descritos em [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md) e [gerenciar equipes durante a transição para o novo Microsoft Teams Centro de administração](manage-teams-skypeforbusiness-admin-center.md).     
    
Os administradores de ti podem adicionar convidados no nível do locatário, definir e gerenciar políticas e permissões do usuário de convidado e receber relatórios sobre atividades do usuário convidado. Esses controles estão disponíveis por meio do centro de administração do Microsoft Teams. O conteúdo e as atividades dos usuários convidados estão sob a mesma proteção de conformidade e auditoria que o restante do Office 365.

Os proprietários da equipe podem convidar novos convidados e adicionar usuários convidados do diretório existente a suas equipes. Os proprietários da equipe podem identificar os usuários convidados por meio do **Teams** > **** Teams e definir recursos relacionados ao canal para convidados por meio do**acesso de convidados**às configurações > de **toda a organização**, incluindo permitir que os convidados criem, atualizem e Exclua os canais, conforme mostrado na ilustração a seguir.

![Configurações de permissões de convidado no Teams](media/manage-guest-access-image1.png)
  
Você pode usar o portal do Azure Active Directory (Azure AD) para gerenciar convidados e seu acesso aos recursos do Office 365 e do teams. O acesso de convidados do teams usa os recursos de colaboração do Azure AD Business-to-Business (B2B) como a infraestrutura subjacente para armazenar informações sobre os princípios de segurança, como propriedades de identidade, associações e configurações de autenticação multi-fator. Para saber mais sobre o Azure AD B2B, confira [o que é colaboração B2B do Azure ad?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [perguntas frequentes sobre colaboração do Active Directory B2B do Azure](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> O Microsoft Teams sempre honra as configurações externas do Azure AD para permitir ou impedir que os usuários convidados sejam adições ao locatário. Para obter mais detalhes, consulte [autorizar o acesso de convidado no Microsoft Teams](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Revisar o acesso de convidado periodicamente

No Teams, você pode adicionar 5 convidados para cada usuário licenciado. Devido a essa limitação ou porque você quer manter seu locatário atualizado, examine o acesso de convidado periodicamente para identificar os usuários que têm acesso a que eles não precisam mais. Você pode usar o Azure AD para criar uma revisão do Access para os membros do grupo ou usuários atribuídos a um aplicativo. Criar análises recorrentes do Access pode poupar tempo. Se precisar revisar rotineiramente os usuários que têm acesso a um aplicativo ou membros de um grupo, você pode definir a frequência dessas análises. 

Você também pode fazer uma crítica de acesso de convidado, pedir aos convidados que examinem sua própria associação ou peça ao proprietário do aplicativo ou ao responsável por decisões comerciais para executar a revisão do Access. Use o portal do Azure para executar análises de acesso de convidado. Para obter mais informações, consulte [gerenciar o acesso de convidados com as críticas do Azure ad Access](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Pré-requisitos

As avaliações do Access estão disponíveis com a versão Premium P2 do Azure AD, que está incluída no Microsoft Enterprise Mobility + Security, e5. Para obter mais informações, consulte [edições do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Cada usuário que interage com esse recurso criando uma revisão, preenchendo uma revisão ou confirmando o acesso dela deve ter uma licença.

O Microsoft Teams não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário é baseado no que o licenciamento do AAD permite. Para obter mais informações, consulte licenciamento de [colaboração B2B do Azure ad](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latências de acesso de convidado

As configurações de convidado são definidas no Azure AD. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o recurso convidado ainda não tenha sido habilitado ou que as configurações ainda não sejam efetivadas.

## <a name="more-information"></a>Mais informações

Para obter informações sobre como usar o PowerShell para gerenciar o acesso de convidados, consulte [usar o PowerShell para controlar o acesso de convidados a uma equipe](guest-access-powershell.md).


