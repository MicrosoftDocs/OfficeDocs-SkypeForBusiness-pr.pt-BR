---
title: Configurar a conectividade híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online.
ms.openlocfilehash: 66f4b25dd1fb4db6951fedd59d7db4697a73822f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293522"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurar a conectividade híbrida entre Skype para Business Server e Office 365
 
**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre Skype para Business Server e do Skype para equipes ou Business Online.  Conectividade híbrida permite que você mova os usuários no local para Skype para Business Online ou equipes e permite que os usuários tirar proveito dos serviços de nuvem.
  
Antes de executar as etapas neste tópico, você deve ter lido [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md).
  
A tabela a seguir lista as tarefas necessárias para configurar o Skype para conectividade híbrida de negócios e fornece links para os artigos associados para obter mais informações.
  
|**Etapa**|**Descrição**|
|:-----|:-----|
|Crie uma conta de locatário para o Office 365 e habilitar Skype para Business Online  <br/> |Saiba mais sobre o Office 365 e Skype para negócios Online no [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para se certificar de que seu ambiente está pronto para o Office 365, consulte os [Requisitos do Sistema](https://products.office.com/en-US/office-system-requirements).  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Introdução ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicionar seu domínio ao seu locatário do Office 365 e verifique a propriedade  <br/> | Você precisa adicionar seu domínio ao seu locatário do Office 365 e, então, seguir as etapas para validar o domínio com o Office 365. Isso serve para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em [Adicionar um domínio ao Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Preparar a sincronização do Active Directory  <br/> |Sincronização do Active Directory mantém seu Active Directory local sincronizado continuamente com o Office 365. Assim, é possível criar versões sincronizadas de cada grupo e conta de usuário e também habilitar a sincronização de lista de endereços global (GAL) do seu ambiente local do Microsoft Exchange Server para o Microsoft Exchange Online. Para obter mais informações, consulte [os diretórios de seu local integra-se com o Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).  <br/>  **Importante:** Você precisa sincronizar as contas do AD do Skype todos os usuários corporativos em sua organização entre seu local e implantações online, mesmo se os usuários não são movidos para Skype para negócios Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários online e locais em sua organização poderá não funcionar como esperado.           |
| Configurar Skype para o híbrido de negócios | Consiste em três etapas:  <br>1. configure seu serviço de borda de local para federação com Skype para negócios Online. <br> 2. configure seu Skype para locatário Business Online para um espaço de endereçamento SIP compartilhado. <br> 3. configure a autenticação, se necessário.    <br> Para obter mais informações, consulte [Configurar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md).
|Mover usuários-piloto  <br/> |Após concluir as etapas para preparar e configurar seu ambiente do Skype para Business Online, você pode iniciar mover usuários piloto para seu locatário do Office 365 online. Para obter mais informações, consulte [mover os usuários no local para Skype para Business Online](move-users-from-on-premises-to-skype-for-business-online.md) e [mover os usuários no local para equipes](move-users-from-on-premises-to-Teams.md).  <br/> | 

  