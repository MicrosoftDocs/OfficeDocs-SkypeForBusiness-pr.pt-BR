---
title: Contas de usuário em ambiente híbrido com PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba mais sobre diferentes combinações de criação de usuário e quais combinações têm suporte ou não têm suporte.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676413"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Contas de usuário em um ambiente híbrido com conectividade PSTN

## <a name="about-the-environment"></a>Sobre o ambiente

Este artigo se aplica a ambientes nos quais você tem todos os seguintes itens:

- Skype for Business Server ou Lync Server 2013
- Uma Microsoft 365 ou Office 365 organização
- Conectividade híbrida configurada entre o Skype for Business Server e o Skype for Business Online ou Microsoft Teams locatário
- Usuários habilitados para fazer e receber chamadas PSTN (Rede Telefônica Pública Comuada) de e para o cliente


Se você tiver um ambiente diferente (como o Skype for Business Cloud Connector Edition), o híbrido não está configurado ou os usuários não estão habilitados para chamadas PSTN, a matriz de suporte será diferente.

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sobre as combinações e a instrução de suporte

Um Skype for Business híbrido com conectividade PSTN fornece flexibilidade sobre onde os serviços de usuário são fornecidos e como as contas de usuário são provisionadas e gerenciadas. Mas a abundância de opções pode criar algumas combinações sem suporte. Esta seção explica diferentes combinações de criação de usuário, seguidas por uma instrução de suporte.

**Definições:**

- **Enterprise Voice:** opção para fornecer acesso ao PSTN para usuários com conta de Skype for Business usuário local. O servidor de mediação Skype for Business local fornece interconectividade ao PSTN.
- **Conectividade de Voz Híbrida:** Opção para fornecer acesso ao PSTN para usuários com Skype for Business Online. O servidor de mediação Skype for Business local fornece interconectividade ao PSTN.
- **Roteamento direto:** Opção para fornecer acesso ao PSTN para usuários com conta de Skype for Business online, Microsoft Teams licença, usando Microsoft Teams cliente. O SBC está conectado ao Proxy SIP no Microsoft 365 ou Office 365 sem a necessidade de nenhum software local da Microsoft.

**O ambiente dá suporte às seguintes combinações:**

- **Cenário 1:** Conta de usuário Skype for Business local e usará o cliente Skype for Business com Enterprise Voice
- **Cenário 2:** Conta de usuário no Skype para empresas online e usará o cliente Skype for Business com Conectividade de Voz Híbrida
- **Cenário 3:** Conta de usuário Skype for Business online com Microsoft Teams e usará Teams cliente

### <a name="supportability-matrix"></a>Matriz de capacidade de suporte

|Objeto de usuário criado em|Provedor de serviços Skype for Business usuário|Cliente do usuário|Opção de voz|Com suporte|
|---|---|---|---|---|
|AD local|No local|Skype for Business|Enterprise Voice|Sim|
|AD local|Online|Skype for Business|Conectividade de Voz Híbrida|Sim|
|AD local|Online|Microsoft Teams|Roteamento Direto|Sim|
|**Combinações sem suporte**|||||
|Azure AD|Local/online|Skype for Business/Microsoft Teams|Enterprise Voice/Conectividade de Voz Híbrida/Roteamento Direto|Não, o objeto de usuário DEVE ser criado no AD local primeiro|
|AD local|No local|Microsoft Teams|Enterprise Voice/Conectividade de Voz Híbrida/Roteamento Direto|Não, Microsoft Teams cliente não é compatível com o Skype for Business|
|AD local|Online|Skype for Business|Roteamento Direto|Não, o Roteamento Direto não é compatível com Skype for Business cliente|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instrução de suporte para o ambiente híbrido com PSTN

Para todos os usuários, o objeto  de usuário deve ser criado no AD local e sincronizado com o Azure AD usando a ferramenta Azure AD Conexão usuário. Não há suporte para habilitar usuários para Teams/Skype for Business  se o objeto de usuário for criado diretamente no Azure AD em uma configuração híbrida. Para novos usuários, como uma nova contratação, que serão habilitados diretamente para o Teams, o usuário deve ser habilitado para Skype for Business usando ferramentas de gerenciamento Skype for Business locais. Não há suporte para a criação de usuários em Skype for Business ou Teams online sem primeiro habilitá-los no pool local com Enterprise Voice **.** Para obter mais informações sobre isso, examine [o plano Sistema de Telefonia com conectividade PSTN local no Skype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
