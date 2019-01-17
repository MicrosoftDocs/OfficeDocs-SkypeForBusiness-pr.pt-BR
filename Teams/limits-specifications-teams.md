---
title: Limites e especificações para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: Saiba mais sobre os limites, especificações e outros requisitos que se aplicam ao Microsoft Teams.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa699ebabd57299ef2ced07c2c6d0fc551ac6b17
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328251"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Limites e especificações para o Microsoft Teams
=============================================

Este artigo descreve algumas dos limites, especificações e outros requisitos que se aplicam ao Microsoft Teams. 

<a name="teams-and-channels"></a>Equipes e canais 
------------------

|Recurso    | Limite máximo |
|-----------|---------------|
|Número de equipes que um usuário pode criar | Sujeito às limit&sup1 250 objeto;         |
|Número de membros da equipe | 2.500       |
|Número de membros em uma [equipe de toda a organização](create-an-org-wide-team.md) | 2.500       |
|Número de equipes que um administrador global pode criar        |  500.000   |
|Número de equipes que pode fazer com que um locatário do Office 365    | 500.000     |
|Número de canais por equipe    | 200 (inclui canais excluídos)         |

&sup1; Qualquer objeto de diretório no Azure Active Directory conta rumo esse limite.

<a name="meetings-and-calls"></a>Reuniões e chamadas 
------------------

|Recurso     | Limite máximo |
|------------|---------------|
|Número de pessoas em uma reunião  | 250    |
|Número de pessoas em um bate-papo privado  | 50    |

<a name="storage"></a>Armazenamento
-------

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Se você não tiver o SharePoint Online habilitado no seu locatário, os usuários do Microsoft Teams sempre não podem compartilhar arquivos em equipes. Os usuários de bate-papo privado também não poderão compartilhar arquivos pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. (Para obter mais informações, consulte [como SharePoint on-line e OneDrive for Business interagem com as equipes da Microsoft](sharepoint-onedrive-interact.md).)

Como equipes é executado em um back-end do SharePoint Online para compartilhamento de arquivos, SharePoint limitações aplicam-se à seção arquivos dentro de uma equipe. Estes são os limites de armazenamento aplicável para o SharePoint Online.

|Recurso                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Armazenamento                 |1 TB por organização mais de 10 GB por licença adquirida  |1 TB por organização mais de 10 GB por licença adquirida  |1 TB por organização mais de 10 GB por licença adquirida   |1 TB por organização mais de 10 GB por licença adquirida |1 TB por organização mais de 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos de equipes |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de carregamento de arquivo       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Cada guia arquivos em equipes é executado em um back-end do SharePoint Online, portanto, os limites de armazenamento acima se aplicam a cada canal dentro de uma equipe.

Para obter mais informações, consulte [limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Mensagens
---------

Os usuários participem de conversas que fazem parte da lista de bate-papo no Microsoft Teams devem ter uma caixa de correio (baseado em nuvem) on-line do Exchange para um administrador pesquisar as conversas de bate-papo. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante de bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Microsoft Teams. Entretanto, nesse caso, o conteúdo dessas conversas não pode ser pesquisada e não pode ser colocada em retenção porque os usuários não possuem caixas de correio baseadas em nuvem. (Para obter mais informações, consulte [como o Exchange e equipes da Microsoft interagir](exchange-teams-interact.md).)

Função de bate-papo do Microsoft Teams funciona em um back-end do Microsoft Exchange, portanto, você pode aplicar limites para a função de bate-papo dentro do Microsoft Teams de mensagens do Exchange. Se os usuários desejam enviar um email a um canal de equipes, ele usará o endereço de email de canal. Depois que um email for parte de um canal, qualquer pessoa pode responder a ele para iniciar uma conversa. Aqui estão alguns dos limites aplicáveis para enviar email a um canal. 

|Recurso  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|Limite de tamanho de mensagem&dagger;  |KB 25   |KB 25   |KB 25   |KB 25   |
|Limite de anexos de arquivo&Dagger;  |20     |20     |20     |20    |
|Limite de imagens embutida&Dagger; |50   |50   |50   |50   |

&dagger;Se a mensagem exceder esse limite, uma mensagem de visualização é gerada e o usuário é solicitado a exibição/download o email original no link fornecido.

&Dagger;Se o número de anexos ou imagens exceder esse limite, a mensagem não será processada e será enviado um email de notificação de falha na volta ao remetente notificando do erro.

Para obter mais informações, consulte [limites do Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Navegadores do  
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Sistemas operacionais
-----------------

Para obter informações sobre os requisitos de sistema operacional, consulte [obter clientes para equipes da Microsoft](get-clients.md).


