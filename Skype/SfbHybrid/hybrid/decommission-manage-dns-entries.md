---
title: Gerenciar entradas DNS ao descomissionar seu ambiente local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como gerenciar entradas DNS ao descomissionar seu ambiente local Skype for Business ambiente.
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458978"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Atualizar entradas DNS para permitir que sua organização seja Teams Somente

As organizações que anteriormente tinham implantações locais do Skype for Business Server ou do Lync Server ainda podem ter entradas DNS que apontem para uma implantação Skype for Business local. Esses registros são necessários se sua organização incluir usuários locais Skype for Business locais. No entanto, uma vez que sua organização não tenha mais nenhum usuário local Skype for Business ou Lync Server, esses registros não serão mais necessários. E, na verdade, como parte da conclusão da migração do local para o Teams, esses registros devem ser atualizados para apontar para Microsoft 365 ou removidos. A Microsoft não pode dar esta etapa para você.

Ao tentar conceder o TeamsOnly a todo o locatário, Teams verificará o DNS para determinar se algum desses registros DNS existe para sua organização. Se algum registro for encontrado e se apontarem para algo diferente de Microsoft 365, a tentativa de alterar o modo de coexistência de locatários para o TeamsOnly falhará por design. Esse design é para impedir que organizações híbridas com usuários locais aplicação incorretamente do modo TeamsOnly ao locatário , pois isso quebraria a federação para todos os usuários locais do Skype for Business (usando o Teams ou Skype for Business).

Além disso, esses registros devem ser atualizados para que você possa conceder o TeamsOnly a todo o locatário.

> [!Note] 
> Em casos raros, a alteração do DNS de apontar no local para o Microsoft 365 para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:
>
> - Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy. Esse modelo de federação herdado não se baseia nos registros SRV DNS, portanto, essa configuração ficará desa datada quando sua organização for para a nuvem.
> 
> - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online. Nesse caso, a federação com essas organizações não funcionará até habilitar seu provedor de hospedagem.
>
> Se você suspeitar que qualquer um de seus parceiros federados possa estar usando Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.

## <a name="how-to-identify-stale-dns-records"></a>Como identificar registros DNS antigos

Para identificar todos os registros DNS que impeçam sua organização de se tornar Teams somente Teams, você pode usar o centro de administração Teams para alterar o modo de coexistência para o TeamsOnly. Vá para **Configuração em toda a**  ->  **organização Teams Atualização**. Quaisquer registros DNS que impeçam que a organização se torne Teams somente serão incluídos na mensagem de erro.  Caso nenhum registro DNS seja encontrado, o modo de coexistência da sua organização será alterado para TeamsOnly. 

## <a name="how-to-remove-stale-dns-records"></a>Como remover registros DNS antigos

Se sua organização não tiver mais usuários locais Skype for Business Server ou Lync Server, faça o seguinte:

- Atualize Skype for Business registros DNS para apontar para Microsoft 365 (em vez da implantação local).

- Remova Skype for Business registros DNS se o domínio SIP não for mais usado. 

Em cada domínio onde você encontrar qualquer um dos seguintes registros, atualize-os da seguinte forma:

| Tipo de registro | Nome | TTL | Prioridade | Peso | Porta | Valor |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls.tcp | 3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip.tls | 3600  | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/D |   N/D |   N/D |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/D |   N/D  | N/D |    sipdir.online.lync.com |
|||||||




