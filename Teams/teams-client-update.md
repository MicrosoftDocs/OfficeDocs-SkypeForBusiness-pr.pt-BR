---
title: Atualizações do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como o cliente de desktop Teams é atualizado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a76fe4e0cfb896d1bd89a02acebc1c00dff8767
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776826"
---
# <a name="teams-update-process"></a>Processo de atualização de equipes

O aplicativo Web Teams é atualizado semanalmente.

As atualizações do cliente de desktop do teams são lançadas a cada duas semanas após rigorosos testes internos e validação por meio do programa de adoção de tecnologia (toque). Geralmente, isso ocorre em uma terça-feira. Se for necessária uma atualização crítica, o Microsoft Teams ignorará esse cronograma e liberará a atualização assim que ela estiver disponível.

O cliente da área de trabalho é atualizado automaticamente. O Teams verifica se há atualizações a cada poucas horas nos bastidores, o descarrega e, em seguida, aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar manualmente as atualizações clicando em **verificar se há atualizações** no menu suspenso **perfil** no canto superior direito do aplicativo. Se houver uma atualização disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar conectados para que as atualizações sejam baixadas. 

A partir de 31 de julho de 2019, as atualizações do cliente do teams usam uma menor largura de banda de rede durante a atualização. Isso é ativado por padrão e não requer nenhuma ação de administradores ou usuários.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E quanto às atualizações do Microsoft 365 para aplicativos Enterprise?

O Teams é instalado por padrão com novas instalações dos aplicativos do Microsoft 365 para empresas, conforme descrito em [implantar o Microsoft Teams com o microsoft 365 aplicativos para empresas](https://docs.microsoft.com/DeployOffice/teams-install). 

O Teams segue seu próprio processo de atualização, conforme descrito acima, e não o processo de atualização para os outros aplicativos do Office, como o Word e o Excel. Para saber mais, leia [visão geral de canais de atualização para aplicativos do Microsoft 365 para empresas](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E quanto às atualizações para o Microsoft Teams no VDI?

Os clientes do teams na Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente da maneira como os clientes de equipes não VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para instalar o Microsoft [Teams no VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar atualizações em vez de atualizações automáticas do teams?

O Microsoft Teams não dá aos administradores a capacidade de implantar atualizações por meio de um mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como um serviço online moderno, o cliente do teams atualiza automaticamente a cada duas semanas. Como as equipes são regidas pela política de ciclo de vida moderno, espera-se que os usuários permaneçam na versão mais atualizada do cliente da área de trabalho. Isso garante que os usuários tenham os recursos mais recentes, aperfeiçoamentos de desempenho, segurança e confiabilidade do serviço.

Para começar a auxiliar na identificação quando os clientes de desktop estiverem desatualizados, um alerta no aplicativo será exibido se a versão atual do usuário estiver entre um e três meses de idade e se houver uma nova versão disponível. Esta mensagem no aplicativo incentiva os usuários a atualizarem para a versão mais recente do teams ou, se necessário, para se comunicar com o administrador de ti. Os usuários de clientes da área de trabalho do teams com mais de três meses verão uma página bloqueada que oferece as opções de atualização agora, entre em contato com o administrador de ti ou continue com o Microsoft Teams na Web.

As versões de cliente da área de trabalho com mais de três meses em primeiro instalar e/ou primeira execução de equipes têm um período de cortesia de 28 dias antes de encontrar as informações de manutenção mencionadas acima. Durante esse período, o processo de atualização automática atualizará o cliente do teams. Se não for atualizado, os usuários verão um alerta no aplicativo incentivando a atualização manual para a versão mais recente do teams ou, se necessário, para acessar o administrador de ti para fazer isso. Isso inclui os usuários que usam o cliente da área de trabalho do teams como parte do pacote de aplicativos do Microsoft 365 para empresas.

Os clientes de desktop do teams nas nuvens governamentais atualmente têm uma exceção para esse contrato de serviço, até que você perceba ainda mais.

Para obter informações sobre as novas versões de versão, verifique o [centro de mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou vá para **ajuda** > **o que há de novo** no cliente.
