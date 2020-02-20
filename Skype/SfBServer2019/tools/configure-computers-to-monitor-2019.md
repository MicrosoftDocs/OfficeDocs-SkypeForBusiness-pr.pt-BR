---
title: Configurar os computadores do Skype for Business Server que serão monitorados
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Instale os arquivos do agente do Operations Manager no computador do Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy do System Center.'
ms.openlocfilehash: ebf859b633a0da047d61a7b0d55c430f81a02401
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150558"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar os computadores do Skype for Business Server que serão monitorados

**Resumo:** Instale os arquivos do agente do Operations Manager no computador do Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy do System Center.

Cada computador do Skype for Business Server 2019 que você deseja monitorar deve ser capaz de autorelatar sua existência ao servidor de gerenciamento. Para habilitar esse processo, você deve instalar os arquivos do agente do Operations Manager em cada um dos computadores a serem monitorados. Após instalar os arquivos de agente, você deve configurar o computador para atuar como um proxy do System Center. Certifique-se de que você instalou e configurou o Skype for Business Server pela primeira vez nesses computadores antes de executar esses procedimentos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro
<a name="watcher_node_outside"> </a>

Os agentes do System Center Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Skype for Business Server), fora da empresa (como um nó do Inspetor de transação sintético externo) ou em um limite de confiança do Active Directory, podem exigir a configuração de um servidor de gateway do System Center Operations Manager. Essa função de servidor habilita agentes que não têm uma relação de confiança com o servidor de gerenciamento raiz para gerar alertas. Para obter detalhes, consulte [Managing gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Se você implantar um agente em um desses locais, você também precisará solicitar e configurar um certificado que permita que o nó do Inspetor envie alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher. Para obter detalhes e baixar esses utilitários, consulte [obtendo certificados para agentes não associados ao domínio simplificados com o assistente de geração de certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Instalando os arquivos do agente do Operation Manager

1. Na mídia de instalação do System Center, clique duas vezes em **Setup. exe**.

2. No assistente de instalação do System Center Operation Manager, clique em **instalar o agente do Operations Manager**, em instalar agente em instalações opcionais

3. No assistente de configuração do System Center, na página Bem-vindo ao assistente de instalação do System Center Operations Manager, clique em **Avançar**.

4. Na página pasta de destino, selecione a pasta onde os arquivos do agente do Operations Manager serão instalados e clique em **Avançar**.

5. Na página configuração do grupo de gerenciamento, selecione **especificar informações do grupo de gerenciamento** e clique em **Avançar**.

6. Na página configuração do grupo de gerenciamento, digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e, em seguida, digite o nome do host do seu servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** . Se você alterou o número da porta usada pelo Operations Manager, insira o novo número da porta na caixa **porta do servidor de gerenciamento** . Caso contrário, deixe a porta no valor padrão de 5723 e, em seguida, clique em **Avançar**.

7. Na página conta de ação do agente, selecione **sistema local** e clique em **Avançar**.

8. Na página Microsoft Update, selecione **eu não desejo usar o Microsoft Update** e clique em **Avançar**.

9. Na página Pronto para Instalar, clique em **Instalar**.

10. Na página Concluindo o assistente de instalação do System Center Operations Manager, clique em **concluir**.

11. Clique em **Sair**.

Para o System Center 2012, você pode verificar se o agente foi criado clicando em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2012**e, em seguida, em **operações do Shell de gerenciamento do 2012**. No Shell do Operations Manager, digite o seguinte comando do Windows PowerShell e pressione ENTER:
```PowerShell
Get-SCOMAgent
```

Será exibida uma lista de todos os seus agentes do Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurando o computador do Skype for Business Server para participar da descoberta do System Center
<a name="watcher_node_outside"> </a>

Para certificar-se de que seu novo agente do Skype for Business Server participa do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager tenha sido instalado:

1. Na guia Administração, clique em **Agente Gerenciado**.

2. Clique no **Assistente de descoberta** e conclua o assistente para que o computador seja descoberto.

3. Reinicialize o serviço do agente de integridade. A reinicialização do serviço forçará a descoberta do novo computador. Se você não reiniciar o serviço, pode levar até 4 horas antes da nova máquina ser descoberta pelo System Center Operations Manager.

4. Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.

5. O computador em que o agente é enviado com êxito será mostrado na lista "gerenciado por agente" e o computador onde o agente foi instalado manualmente será mostrado em "gerenciamento pendente", clique no nome do computador e aprove.

6. Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.


