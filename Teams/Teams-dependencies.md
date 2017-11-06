---
title: "Dependências do Office 365 para o Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: O Microsoft Teams depende dos grupos do Office 365, do SharePoint Online e do OneDrive for Business.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Dependências do Office 365 para o Microsoft Teams
===========================================

O Microsoft Teams depende dos grupos do Office 365 para armazenar assinaturas equipes e outras propriedades, como configurações de classificação de dados da equipe. Os grupos do Office 365 são um serviço que oferece assinatura cruzada de aplicativos para um conjunto de ativos compartilhados de equipe, como um site do SharePoint ou um painel de controle do Power BI, para que a equipe possa colaborar de forma eficaz e segura. 

O Teams também depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo. Além disso, o Teams depende dos grupos do Office 365 para armazenar assinaturas equipes e outras propriedades, como configurações de classificação de dados da equipe. Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).
  
    
    
Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:
  
    
    

- No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**
    
    Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**
    
    Para obter mais informações, consulte [Controle do acesso de convidados no Microsoft Teams](#controlguest).
  

Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams. Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).