---
title: Configurar os computadores do Skype for Business Server que serão monitorados
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Resumo: Instale os arquivos de agente do Operations Manager no computador do Skype for Business Server 2015 a ser monitorado e configure o computador para atuar como um proxy do System Center.'
ms.openlocfilehash: d3935f0f6c9ffb13ac18f544d7b4727199b6dbea
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814881"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurar os computadores do Skype for Business Server que serão monitorados

**Resumo:** Instale os arquivos de agente do Operations Manager no computador do Skype for Business Server 2015 a ser monitorado e configure o computador para atuar como um proxy do System Center.

Cada computador do Skype for Business Server 2015 que você deseja monitorar deve ser capaz de auto-relatar sua existência ao servidor de gerenciamento. Para habilitar esse processo, você deve instalar os arquivos de agente do Operations Manager em cada um dos computadores a serem monitorados. Depois de instalar os arquivos de agente, você deve configurar o computador para atuar como um proxy do System Center. Primeiro, instale e configure o Skype for Business Server nesses computadores antes de realizar esses procedimentos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro
<a name="watcher_node_outside"> </a>

Agentes do System Center Operations Manager em execução em uma rede de perímetro (como um Servidor de Borda do Skype for Business Server), fora da empresa (como um nó do watcher de transação sintética externa) ou em um limite de confiança do Active Directory, podem exigir a configuração de um System Center Operations Manager Gateway Server. Essa função de servidor permite que agentes que não tenham uma relação de confiança com o Servidor de Gerenciamento Raiz ativem alertas. Para obter detalhes, [consulte Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Se você implantar um agente em um desses locais, também precisará solicitar e configurar um certificado que habilita o nó do watcher a enviar alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher. Para obter detalhes e baixar esses [utilitários, consulte Obtendo certificados](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)para agentes que não ingressaram no domínio foram facilitados com o Assistente de Geração de Certificado.

### <a name="installing-the-operation-manager-agent-files"></a>Instalando os arquivos de agente do Operation Manager

1. Na mídia de instalação do System Center, clique duas vezes **Setup.exe**.

2. No assistente de configuração do System Center Operation Manager, clique em Instalar o Agente do **Operations Manager,** em Agente de Instalação em Instalações Opcionais

3. No assistente de configuração do System Center, na página Bem-vindo ao assistente de Instalação do System Center Operations Manager, clique em **Próximo.**

4. Na página Pasta de Destino, selecione a pasta onde os arquivos do Agente do Operations Manager serão instalados e clique em **Próximo.**

5. Na página Configuração do Grupo de Gerenciamento, selecione Especificar informações **do Grupo de Gerenciamento** e clique em **Próximo.**

6. Na página Configuração do Grupo de Gerenciamento, digite  o nome do seu Grupo de Gerenciamento do Operations Manager na caixa Nome do Grupo de Gerenciamento  e digite o nome de host do seu servidor do Operations Manager (por exemplo, atl-scom-001) na caixa Servidor de Gerenciamento. Se você alterou o número da porta usada pelo Operations Manager, insira o novo número da porta na caixa **Porta do Servidor de** Gerenciamento. Caso contrário, deixe a porta com o valor padrão de 5723 e clique em **Próximo.**

7. Na página Conta de Ação do Agente, selecione **Sistema Local** e clique em **Próximo.**

8. Na página do Microsoft Update, selecione Não quero usar **o Microsoft Update** e clique em **Próximo.**

9. Na página Pronto para Instalar, clique em **Instalar**.

10. Na página Concluindo o assistente de Configuração do System Center Operations Manager, clique em **Concluir.**

11. Clique em **Sair**.

Para o System Center 2012, você pode verificar se o agente foi criado clicando em Iniciar **,** em Todos os **Programas,** em **System Center Operations Manager 2012** e em Shell do Gerenciador do **Operations 2012.** No Shell do Operations Manager, digite o seguinte comando do Windows PowerShell e pressione ENTER:
```PowerShell
Get-SCOMAgent
```

Uma lista de todos os agentes do Operations Manager será exibida.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurando o computador do Skype for Business Server para participar do System Center Discovery
<a name="watcher_node_outside"> </a>

Para garantir que seu novo agente do Skype for Business Server participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador onde o console do System Center Operations Manager foi instalado:

1. Na guia Administração, clique em **Agente Gerenciado**.

2. Clique no **Assistente de Descoberta** e conclua o assistente para o computador a ser descoberto.

3. Reinicialize o serviço agente de saúde. Reiniciar o serviço forçará a descoberta do novo computador. Se você não reiniciar o serviço, poderá levar até 4 horas antes que o novo computador seja descoberto pelo System Center Operations Manager.

4. Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.

5. O computador onde o agente é pressionado com êxito será mostrado na lista "Agente Gerenciado" e o computador onde o agente foi instalado manualmente será mostrado em "Gerenciamento Pendente", clique no nome do computador e aprove.

6. Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.


