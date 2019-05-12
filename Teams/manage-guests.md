---
title: Gerenciar o acesso de convidados no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44769df812e667ab5b108dcb42d8bb96453f15af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885102"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gerenciar o acesso de convidados no Microsoft Teams
======================================

**Convidado** é um tipo de licença de usuário/na Microsoft Teams que está incluído com todas as inscrições de educação do Office 365, Office 365 Enterprise e Business Premium do Office 365. Não é necessária nenhuma licença adicional do Office 365. O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão. Para obter detalhes sobre como habilitar o acesso de convidado, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).

Depois que o tipo de licença de **usuário/Convidado** está ativado, você pode definir configurações para convidados por meio dos controles descritas nas [configurações de gerenciar equipes da Microsoft para a sua organização](enable-features-office-365.md) e [gerenciar equipes durante a transição para o novo Teams da Microsoft Centro de administração](manage-teams-skypeforbusiness-admin-center.md).     
    
Administradores de TI podem adicionar convidados a nível de locatário, definir e gerenciar permissões e as diretivas de usuário convidado e recepção relatórios sobre as atividades do usuário convidado. Esses controles estão disponíveis por meio do Centro de administração do Microsoft Teams. O conteúdo e as atividades dos usuários convidados estão sob a mesma proteção de conformidade e auditoria que o restante do Office 365.

Os proprietários de equipe podem convidar novos convidados e adicionar usuários existentes do diretório convidado a suas equipes. Os proprietários de equipe podem identificar usuários convidados por meio de **equipes** > **gerenciar equipes**e recursos relacionados à canal de conjunto de convidados por meio de **configurações de toda a organização** > **acesso como convidado**, incluindo permitir que os convidados criar, atualizar, e Exclua canais, conforme mostrado na seguinte imagem.

![Configurações de permissões de convidado em equipes](media/manage-guest-access-image1.png)
  
Você pode usar o portal do Azure Active Directory para gerenciar seu acesso ao Office 365 e recursos de equipes e convidados. O acesso de convidados das equipes faz uso dos recursos de colaboração entre empresas (B2B) do Azure Active Directory como a infraestrutura subjacente para armazenar informações de princípios de segurança, como propriedades de identidade, assinaturas e configurações de autenticação multifator. Para saber mais sobre o Azure Active Directory B2B, consulte [O que é a colaboração do Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [Perguntas frequentes de colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams sempre respeita configurações externas do Azure Active Directory para permitir ou impedir adições de usuário convidado para o inquilino. Para obter mais detalhes, consulte [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md).
  
## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>Revise periodicamente o acesso de convidado

Em equipes, você pode adicionar 5 convidados para cada usuário licenciado. Devido a essa limitação, ou porque você deseja manter seu locatário atualizado, você deve revisar o acesso de convidado periodicamente para identificar usuários que têm acesso eles não são mais necessitam. Você pode usar o Windows Azure Active Directory (AD Azure) para criar uma revisão de acesso para os usuários atribuídos a um aplicativo ou de membros do grupo. Criando recorrente acesso revisões pode economizar tempo para você. Se você precisar rotineiramente, revise os usuários que têm acesso a um aplicativo ou são membros de um grupo, você pode definir a frequência das revisões. 

Você pode realizar uma análise de acesso de convidado sozinho, peça convidados para examinar suas próprias associações ou pedir um proprietário do aplicativo ou o tomador de decisões de negócios para realizar a análise de acesso. Você pode usar o portal do Windows Azure para a realização de análises de acesso de convidado. Para obter mais informações, consulte [Gerenciar o acesso de convidado com acesso do Azure AD analisa](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites"></a>Pré-requisitos

Avaliações de acesso estão disponíveis com a edição Premium P2 do Azure AD, que está incluído no Microsoft Enterprise mobilidade + segurança, E5. Para obter mais informações, consulte "Escolher uma edição" nas [edições do Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis). Cada usuário que interage com esse recurso Criando uma revisão, preenchendo uma revisão ou confirmando seu acesso, deve ter uma licença. 

As equipes não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário baseia-se nos quais licenciamento sua AAD permite. Para obter mais informações, consulte [Licenciamento de colaboração do Windows Azure AD B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="guest-access-latencies"></a>Latências de acesso de convidado

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vê a mensagem "Contate o administrador" ao tentar adicionar um convidado para sua equipe, é provável que o recurso de convidado ainda não foi ativado ou as configurações ainda não estejam efetivas.

## <a name="more-information"></a>Mais informações

Para obter informações sobre como usar o PowerShell para gerenciar o acesso de convidado, consulte [Usar o PowerShell para controlar o acesso de convidado para uma equipe](guest-access-powershell.md).


