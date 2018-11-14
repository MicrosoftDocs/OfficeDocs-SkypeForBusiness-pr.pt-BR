---
title: Gerenciamento do acesso de convidados no Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 11/13/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: rramesan
search.appverid: MET150
description: Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 143170c6a7a174d35300b73693f0a828336b7d32
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510564"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gerenciamento do acesso de convidados no Microsoft Teams
======================================

**Convidado** é um tipo de licença de usuário/na Microsoft Teams que está incluído com todas as inscrições de educação do Office 365, Office 365 Enterprise e Business Premium do Office 365. Não é necessária nenhuma licença adicional do Office 365. O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão. Para obter detalhes sobre como habilitar o acesso de convidado, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).

Depois que o tipo de licença de **usuário/Convidado** está ativado, você pode definir configurações para convidados por meio dos controles descritas na [dos [recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md) e gerenciar equipes durante a transição para o novo sistema operacional Microsoft Equipes e Skype para Business Admin Center](manage-teams-skypeforbusiness-admin-center.md).     
    
Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado. Esses controles estão disponíveis no centro de administração do Office 365. O conteúdo e as atividades dos usuários convidados estão sob a mesma proteção de conformidade e auditoria que o restante do Office 365.

Os proprietários de equipe podem convidar novos convidados e adicionar usuários existentes do diretório convidado a suas equipes. Além disso, os proprietários de equipe podem definir capacidades relacionadas à canal para convidados por meio de **gerenciar equipes** > **permissões de convidado**, incluindo permitir que os convidados criar, atualizar e excluir canais, conforme mostrado na seguinte imagem:

![Configurações de permissões de convidado em equipes.](media/view-guests-guest-permissions.png)
  

Além disso, você pode usar o portal do Azure Active Directory para gerenciar os convidados e o seu acesso aos recursos do Office 365 e do Teams. O acesso de convidados das equipes faz uso dos recursos de colaboração entre empresas (B2B) do Azure Active Directory como a infraestrutura subjacente para armazenar informações de princípios de segurança, como propriedades de identidade, assinaturas e configurações de autenticação multifator. Para saber mais sobre o Azure Active Directory B2B, consulte [O que é a colaboração do Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [Perguntas frequentes de colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Microsoft Teams sempre respeita configurações externas do Azure Active Directory para permitir ou impedir adições de usuário convidado para o inquilino. Para obter mais detalhes, consulte [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md).
  
## <a name="guest-access-latencies"></a>Latências de acesso de convidado

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vê a mensagem "Contate o administrador" ao tentar adicionar um convidado para sua equipe, é provável que o recurso de convidado ainda não foi ativado ou as configurações ainda não estejam efetivas.