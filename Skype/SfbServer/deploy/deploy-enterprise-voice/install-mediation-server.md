---
title: Instalar os arquivos do servidor de mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: saiba como instalar os arquivos do servidor de mediação no Skype for Business Server.'
ms.openlocfilehash: 4dc4c9971b74bf27d0f516ed70484646b666a845
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767114"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar os arquivos do servidor de mediação no Skype for Business Server
 
**Resumo:** Saiba como instalar os arquivos do servidor de mediação no Skype for Business Server.
  
Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.
  
Use as etapas neste tópico para executar o assistente de implantação do Skype for Business Server para instalar os arquivos do servidor de mediação em um computador que você adicionou a um pool do servidor de mediação depois de ter usado o construtor de topologias para definir e publicar o pool. Ao instalar o servidor de mediação de arquivos, você também instala e atribui o certificado necessário para cada computador em um pool do servidor de mediação. 
  
> [!NOTE]
> Este tópico pressupõe que você já definiu e publicou um pool autônomo do servidor de mediação em sua topologia, conforme descrito em [implantar um servidor de mediação no construtor de topologias no Skype for Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1. Na mídia de instalação, clique com o botão direito do mouse em _ \<instalação do Media\> _ **\Setup\amd64\Setup.exe**e clique em **Executar como administrador**.
    
2. Na página **Local de instalação**, clique em **OK**.
    
3. Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)
    
4. Na página do **Assistente de implantação do Skype for Business Server** , clique em **instalar ou atualizar o sistema do Skype for Business Server**.
    
5. Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.
    
6. Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.
    
7. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
8. Ao lado da **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **executar**e clique em **Avançar**.
    
9. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribuí-lo.
    
11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.
    
12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.
    
13. No computador em que você está executando o painel de controle do Skype for Business Server, verifique na página **Topology** do painel de controle do Skype for Business Server que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**. 
    
Se você adicionou mais de um computador ao pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação. Se você não precisar instalar arquivos para o servidor de mediação para qualquer outro computador, siga os procedimentos em [Configurar troncos no Skype for Business Server](configure-trunks.md) para definir configurações para a conexão de tronco entre este pool de servidores de mediação (ou todos os servidores de mediação em um site) e seu par.

