---
title: Expansor de Configurações de Implantação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 'É possível editar as propriedades de uma implantação existente com as seguintes seções:'
ms.openlocfilehash: d9a42dffe3782a84b90b8cecbbc2af2835871732
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878088"
---
# <a name="deployment-settings-expander"></a>Expansor de Configurações de Implantação

É possível editar as propriedades de uma implantação existente com as seguintes seções:

- Domínio SIP

- URLs simples 

- Servidor de Gerenciamento Central

## <a name="sip-domain"></a>Domínio SIP

Para editar o **Domínio SIP padrão**, insira o nome de domínio novo.

Para adicionar **Domínios SIP com suporte adicionais**, digite o nome do nome de domínio que você precisa adicionar. Clique em **Adicionar** para aceitá-lo como o novo nome de domínio do protocolo SIP.

Para atualizar um nome de domínio SIP adicional existente, selecione o nome de domínio e faça alterações na caixa de texto. Clique em   **Atualizar** para aceitar a alteração.

Para remover um nome de domínio SIP adicional definido, selecione o nome de domínio e clique em **Remover**.

Quando concluir todas as alterações na página Editar Propriedades, clique em **OK** para salvá-las. Clique em **Cancelar** para descartar as alterações.

## <a name="simple-urls"></a>URLs simples

Para definir ou modificar URLs simples, decida qual das três URL simples você prefere editar ou alterar. É possível escolher entre URL de acesso telefônico, URL de reunião e URL de acesso administrativo.

Para modificar a URL de acesso telefônico ou a URL de reunião, selecione a URL que deseja alterar. Clique em  **Editar URL**. Em seguida, edite a URL e clique em **OK** para salvar a URL. Clique em **Cancelar** para descartar quaisquer alterações.

Para adicionar uma nova URL, clique em **Adicionar**. Na caixa de diálogo **Adicionar URL simples** especifique a URL e clique em **OK** para salvar a URL. Selecione **Tornar esta a URL ativa para o domínio selecionado** caso necessite definir a nova URL como URL ativa. Clique em **Cancelar** para descartar quaisquer alterações.

Para tornar outra URL diferente a URL ativa (conforme indicado pela marca de seleção verde ao lado da URL), selecione a URL e clique em **Tornar Ativo**.

> [!NOTE]
> Só pode haver uma URL ativa para cada domínio SIP.

Caso precise remover a URL, selecione-a e clique em **Remover**.

> [!CAUTION]
> Leia com atenção as informações na página da caixa de diálogo de configurações de URLs simples. Remover uma URL de reunião pode fazer com que as reuniões agendadas por usuários não possam mais ser acessadas. Considere deixar a URL antiga após ativar a nova URL de reunião. Quando estiver certo de que os usuários não estão mais usando a URL de reunião antiga, você poderá removê-la com segurança.

Para editar ou alterar a URL de acesso Administrativo, edite a entrada.

Quando concluir todas as alterações na página Editar Propriedades, clique em **OK** para salvá-las. Clique em **Cancelar** para descartar as alterações.

## <a name="central-management-server"></a>Servidor de Gerenciamento Central

O Servidor de Gerenciamento Central pode ser alterado de um pool de Front-Ends definido para outro pool de Front-Ends definido. Para alterar o local do Servidor de Gerenciamento Central, selecione na lista suspensa o pool de Front-Ends em **Servidor Front-End no qual instalar o Servidor de Gerenciamento Central em:**. Um Servidor Front-End pode ser um pool de Front-Ends Enterprise Edition ou um Servidor Front-End Standard Edition.

> [!IMPORTANT]
> Depois de definir, publicar e implantar o repositório de Gerenciamento Central da infraestrutura, você não pode mudar o local do repositório de Gerenciamento Central sem realocar o repositório de Gerenciamento Central para outro Front-End por meio de um processo externo.

Para obter detalhes sobre como mover o repositório do Servidor de Gerenciamento Central, consulte [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) na referência de cmdlet do Windows PowerShell.

## <a name="see-also"></a>Consulte Também

Para obter detalhes sobre como definir e configurar estas configurações, consulte [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).


