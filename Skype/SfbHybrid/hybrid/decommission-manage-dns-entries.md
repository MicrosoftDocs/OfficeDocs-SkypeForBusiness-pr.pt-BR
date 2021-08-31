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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como gerenciar entradas DNS ao descomissionar seu ambiente local Skype for Business ambiente.
ms.openlocfilehash: 70255314ecf87d55ef578a4daa0390b46179349c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58735318"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>Atualizar entradas DNS para permitir que sua organização seja Teams Somente

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

As organizações que anteriormente tinham implantações locais do Skype for Business Server ou do Lync Server ainda podem ter entradas DNS que apontem para uma implantação Skype for Business local. Esses registros são necessários se sua organização incluir usuários locais Skype for Business locais. No entanto, uma vez que sua organização não tenha mais usuários locais do Skype for Business ou do Lync Server, esses registros originais não são mais exigidos pela implantação local e essas entradas DNS devem ser atualizadas para apontar para o Microsoft 365 (ou, em alguns casos, **removidos)** como parte da migração do local para o Teams Only. *A Microsoft não pode atualizar esses registros DNS em seu nome.*

Ao tentar conceder o TeamsOnly a todo o locatário, o Teams verificará o DNS para determinar se algum desses registros DNS listados abaixo existe em cada um dos domínios verificados Microsoft 365 em sua organização. Se algum registro for encontrado e se apontarem para algo diferente de Microsoft 365, a tentativa de alterar o modo de coexistência de locatários para o TeamsOnly falhará por design. Isso impede que as organizações híbridas com usuários locais aplicação incorretamente do modo TeamsOnly ao locatário , pois isso quebraria a federação para todos os usuários locais Skype for Business na organização (seja usando o Teams ou Skype for Business).


## <a name="how-to-identify-stale-dns-records"></a>Como identificar registros DNS antigos

Para identificar todos os registros DNS que impeçam sua organização de se tornar Teams somente Teams, você pode usar o centro de administração Teams para alterar o modo de coexistência para o TeamsOnly. Vá para **Configuração em toda a**  ->  **organização Teams Atualização**. Quaisquer registros DNS que impeçam que a organização se torne Teams somente serão incluídos na mensagem de erro.  Caso nenhum registro DNS seja encontrado, o modo de coexistência da sua organização será alterado para TeamsOnly.   

Como alternativa, você pode usar Teams PowerShell para fazer o mesmo, conforme mostrado abaixo:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
   ```

## <a name="dns-records-to-be-updated"></a>Registros DNS a serem atualizados

Se sua organização não tiver mais usuários hospedados no Skype for Business Server local ou no Lync Server, faça o seguinte:

- Atualize a Skype for Business de registros DNS abaixo para apontar para Microsoft 365 (em vez da implantação local). Se você tiver mais de um domínio SIP, deverá fazer isso para cada domínio SIP que seja um domínio Microsoft 365 verificado.

- Remova Skype for Business registros DNS se o domínio SIP não for mais usado. 

Em cada domínio onde você encontrar qualquer um dos seguintes registros, atualize-os da seguinte forma:

| Tipo de registro | Nome | TTL | Prioridade | Peso | Porta | Valor |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls._tcp |    3600 |  100 | 1 | 5061  | sipfed.online.lync.com |
| SRV | _sip._tls | 3600     | 100 |    1   | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  N/D |   N/D |   N/D |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    N/D |   N/D  | N/D |    sipdir.online.lync.com |
|||||||

Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos. Por fim, quaisquer registros DNS para Skype for Business em sua rede interna devem ser removidos.

> [!Note] 
> Em casos raros, a alteração do DNS de apontar no local para o Microsoft 365 para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:
>
> - Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy. Esse modelo de federação herdado não se baseia nos registros SRV DNS, portanto, essa configuração ficará desa datada quando sua organização for para a nuvem.
> 
> - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online. Nesse caso, a federação com essas organizações não funcionará até habilitar seu provedor de hospedagem.
>
> Se você suspeitar que qualquer um de seus parceiros federados possa estar usando Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.
  




