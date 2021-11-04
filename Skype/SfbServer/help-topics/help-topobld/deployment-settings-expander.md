---
title: Expansor de Configurações de Implantação
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 'Você pode editar as propriedades de uma implantação existente com as seguintes seções:'
ms.openlocfilehash: e0904911dc5e1ae7edd49b86e33fa34599ac23d6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773931"
---
# <a name="deployment-settings-expander"></a>Expansor de Configurações de Implantação

Você pode editar as propriedades de uma implantação existente com as seguintes seções:

- Domínio SIP

- URLs simples

- Servidor de Gerenciamento Central

## <a name="sip-domain"></a>Domínio SIP

Para editar o  **Domínio SIP padrão**, insira o nome de domínio novo.

Para adicionar  **Domínios SIP adicionais com suporte**, digite o nome do nome de domínio que você precisa adicionar. Clique em  **Adicionar** para aceitá-lo como o novo nome de domínio SIP (Session Initiation Protocol).

Para atualizar um nome de domínio SIP adicional existente, selecione o nome de domínio e faça alterações na caixa de texto. Clique em  **Atualizar** para aceitar a alteração.

Para remover um nome de domínio SIP adicional definido, selecione o nome de domínio e clique em  **Remover**.

Quando concluir todas as mudanças na página Editar Propriedades, clique em **OK** para salvar as mudanças. Clique em  **Cancelar** para descartar as mudanças.

## <a name="simple-urls"></a>URLs simples

Para definir ou modificar URLs simples, você decide qual das três URLs simples você irá editar ou modificar. É possível escolher entre URL de acesso telefônico, URL de reunião e URL de acesso administrativo.

Para modificar a URL de acesso ao Telefone ou a URL de Reunião, selecione a URL que você deseja alterar. Clique em **Editar URL**. Em seguida, edite a URL e clique em **OK** para salvar a URL. Clique em **Cancelar** para descartar quaisquer alterações.

Para adicionar uma nova URL, clique em  **Adicionar**. Na caixa de diálogo  **Adicionar URL simples** especifique a URL e clique em  **OK** para salvar a URL. Selecione  **Tornar esta URL ativa para o domínio selecionado** caso necessite definir a nova URL como URL ativa. Clique em  **Cancelar** para descartar quaisquer mudanças.

Para tornar uma URL diferente a URL ativa (conforme indicado pela marca de seleção verde ao lado da URL), selecione a URL e clique em **Tornar Ativa**.

> [!NOTE]
> Só pode haver uma URL ativa para cada domínio SIP.

Caso precise remover a URL, selecione-a e clique em  **Remover**.

> [!CAUTION]
> Leia com atenção as informações na página de diálogo de configurações de URLs simples. Remover uma URL de reunião pode fazer com que as reuniões agendadas por usuários não possam mais ser acessadas. Considere deixar a URL antiga após ativar a nova URL de reunião. Quando estiver certo de que os usuários não estão mais usando a URL de reunião antiga, você poderá removê-la com segurança.

Para editar ou alterar a URL de acesso administrativo, edite a entrada.

Quando concluir todas as mudanças na página Editar Propriedades, clique em **OK** para salvar as mudanças. Clique em  **Cancelar** para descartar as mudanças.

## <a name="central-management-server"></a>Servidor de Gerenciamento Central

O Servidor Central de Gerenciamento pode ser alterado de um pool de Front-Ends definido para outro pool de Front-Ends definido. Para alterar o local do Servidor Central de Gerenciamento, selecione na lista suspensa o pool de Front-Ends em  **Servidor Front-End no qual instalar o Servidor Central de Gerenciamento**. Um Servidor Front-End pode ser um pool de Front-Ends Enterprise Edition ou um Servidor Front-End Standard Edition.

> [!IMPORTANT]
> Depois de definir, publicar e implantar o repositório de Gerenciamento Central para a infraestrutura, você não pode mudar o local do repositório de Gerenciamento Central sem realocar o repositório de Gerenciamento Central para outro Front-End via um processo externo.

Para obter detalhes sobre como mover o armazenamento de Gerenciamento Central, consulte [Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps) na referência Windows PowerShell cmdlet.

## <a name="see-also"></a>Confira também

Para maiores detalhes sobre como definir e configurar estas configurações, consulte  [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology).