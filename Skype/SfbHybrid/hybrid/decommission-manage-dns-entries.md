---
title: Gerenciar entradas DNS ao desativar seu ambiente local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como gerenciar entradas DNS ao desativar o ambiente de Skype for Business local.
ms.openlocfilehash: c21a736c19ecec41ddc0458931675ca8ede34ed2
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671877"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Atualizar entradas DNS para permitir que sua organização seja Teams Somente

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

As organizações que anteriormente tinham implantações locais do Skype for Business Server ou do Lync Server ainda podem ter entradas DNS que apontam para uma implantação Skype for Business local. Esses registros serão necessários se sua organização incluir usuários Skype for Business locais. No entanto, depois que sua organização não tiver mais usuários locais do Skype for Business ou do Lync Server, esses registros originais não serão mais exigidos pela implantação local e essas entradas DNS deverão ser atualizadas para apontar para **o Microsoft 365 (** ou, em alguns casos, removidos) como parte da migração do local para o Teams Somente. *A Microsoft não pode atualizar esses registros DNS em seu nome.*

Ao tentar conceder o TeamsOnly a todo o locatário, o Teams verificará o DNS para determinar se algum desses registros DNS listados abaixo existe em cada um dos domínios Microsoft 365 verificados em sua organização. Se algum registro for encontrado e se apontarem para algo diferente de Microsoft 365, a tentativa de alterar o modo de coexistência do locatário para TeamsOnly falhará por design. Isso impede que organizações híbridas com usuários locais apliquem erroneamente o modo TeamsOnly ao locatário, pois isso interromperia a federação para todos os usuários locais do Skype for Business na organização (usando Teams ou Skype for Business).

## <a name="how-to-identify-stale-dns-records"></a>Como identificar registros DNS obsoletos

Para identificar todos os registros DNS que impeçam que sua organização se torne Teams, você pode usar o centro de administração do Teams para alterar o modo de coexistência para TeamsOnly. Vá para **Teams** >  **Teams de atualização**. Todos os registros DNS que impedem que a organização se torne Teams somente serão incluídos na mensagem de erro.  Caso nenhum registro DNS seja encontrado, o modo de coexistência da sua organização será alterado para TeamsOnly.

Como alternativa, você pode usar Teams PowerShell para fazer a mesma coisa, conforme mostrado abaixo:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Registros DNS a serem atualizados

Se sua organização não tiver mais usuários hospedados no Skype for Business Server ou no Lync Server, você deverá fazer o seguinte:

- Atualize Skype for Business lista de registros DNS abaixo para apontar para Microsoft 365 (em vez da implantação local). Se você tiver mais de um domínio SIP, deverá fazer isso para cada domínio SIP que seja um Microsoft 365 verificado.

- Remova Skype for Business registros DNS se o domínio SIP não for mais usado.

Em cada domínio em que você encontrar qualquer um dos seguintes registros, atualize-os da seguinte maneira:

|Tipo de registro|Nome|TTL|Prioridade|Peso|Porta|Valor|
|---|---|---|---|---|---|---|
|SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync.com|
|SRV|_sip._tls|3600|100|1|443|sipdir.online.lync.com|
|CNAME|lyncdiscover|3600|N/D|N/D|N/D|webdir.online.lync.com|
|CNAME|sip|3600|N/D|N/D|N/D|sipdir.online.lync.com|

Além disso, os registros CNAME para reunir ou dialin (se presente) podem ser excluídos. Por fim, todos os registros DNS Skype for Business em sua rede interna devem ser removidos.

> [!NOTE]
> Em casos raros, alterar o DNS de apontar localmente para Microsoft 365 para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:
>
> - Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy. Esse modelo de federação herdado não se baseia em registros SRV dns, portanto, essa configuração ficará desatualizada quando sua organização for movida para a nuvem.
>
> - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync.<span> com precisará atualizar sua configuração para habilitar isso. Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com nenhum locatário híbrido ou online. Nesse caso, a federação com essas organizações não funcionará até que habilitem seu provedor de hospedagem.
>
> Se você suspeitar que qualquer um de seus parceiros federados esteja usando a Federação Direta ou não tenha federado com nenhuma organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso à medida que se prepara para concluir sua migração para a nuvem.
