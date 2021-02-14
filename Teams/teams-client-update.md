---
title: Atualizações do Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Neste artigo, você aprenderá sobre o processo por trás da atualização do cliente de área de trabalho do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8681f3f4cc7c25e9499e25e3978848084086a2a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031877"
---
# <a name="teams-update-process"></a>Processo de atualização do Teams

O aplicativo Web do Teams é atualizado semanalmente.

As atualizações do cliente de área de trabalho do Teams são lançadas a cada duas semanas após testes internos rigorosos e validação por meio do nosso Programa de Adoção de Tecnologia (TAP). Isso geralmente ocorre em uma terça-feira. Se uma atualização crítica for necessária, o Teams ignorará esse cronograma e lançará a atualização assim que estiver disponível.

O cliente da área de trabalho é atualizado automaticamente. O Teams verifica se há atualizações a cada poucas horas nos bastidores, baixa-as e, em seguida, espera o computador ficar ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar atualizações manualmente clicando em Verificar se há atualizações no menu suspenso Perfil no canto superior direito do aplicativo.   Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar assinados para que as atualizações sejam baixadas. 

A partir de 31 de julho de 2019, as atualizações de cliente do Teams usam largura de banda de rede significativamente menor durante a atualização. Isso é ligado por padrão e não requer nenhuma ação de administradores ou usuários.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E quanto às atualizações dos aplicativos microsoft 365 para empresas?

O Teams é instalado por padrão com novas instalações do Microsoft 365 Apps para empresas, conforme descrito em Implantar o Microsoft Teams com o [Microsoft 365 Apps para empresas.](https://docs.microsoft.com/DeployOffice/teams-install) 

O Teams segue seu próprio processo de atualização conforme descrito acima, e não o processo de atualização para os outros aplicativos de Escritórios, como o Word e o Excel. Para saber mais, leia Visão [geral dos canais de atualização para aplicativos do Microsoft 365 para empresas](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E quanto às atualizações do Teams no VDI?

Os clientes do Teams na VDI (Virtual Desktop Infrastructure) não são atualizados automaticamente da mesma forma que os clientes que não são do Teams VDI. Você precisa atualizar a imagem do VM instalando um novo MSI conforme descrito nas instruções para instalar o [Teams no VDI.](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi) Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar atualizações em vez de atualizar automaticamente o Teams?

O Teams não dá aos administradores a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como um serviço online moderno, o cliente teams é atualizado automaticamente a cada duas semanas. Como o Teams é regido pela Política de Ciclo de Vida Moderna, espera-se que os usuários permaneçam na versão mais atualizada do cliente da área de trabalho. Isso garante que os usuários tenham os recursos mais recentes, melhorias de desempenho, segurança e confiabilidade do serviço.

Para começar a ajudar a identificar quando os clientes da área de trabalho estão desacordos, um alerta no aplicativo será exibido se a versão atual do usuário tiver entre um e três meses e se houver uma nova versão disponível. Essa mensagem no aplicativo incentiva os usuários a atualizar para a versão mais recente do Teams ou, se necessário, a entrar em contato com o administrador de IT para fazer isso. Os usuários em clientes de área de trabalho do Teams com mais de três meses verão uma página de bloqueio que oferece as opções para atualizar agora, falar com o administrador de EQUIPE ou continuar com o Teams na Web.

As versões do cliente da área de trabalho com mais de três meses após a primeira instalação e/ou a primeira executar do Teams têm um período de carência de 28 dias antes de encontrar as informações de manutenção mencionadas acima. Durante esse período, o processo de atualização automática atualizará o cliente do Teams. Se não for atualizado, os usuários verão um alerta no aplicativo incentivando-os a atualizar manualmente para a versão mais recente do Teams ou, se necessário, a entrar em contato com o administrador de IT para fazer isso. Isso inclui os usuários que usam o cliente de área de trabalho do Teams como parte do pacote aplicativos do Microsoft 365 para empresas.

Os clientes da área de trabalho do Teams em Nuvens governamentais têm atualmente uma exceção para este contrato de manutenção até aviso prévio.

Para obter informações sobre versões novas, [verifique](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o Centro de Mensagens ou acesse **Ajuda** sobre as novidades  >   do cliente.
