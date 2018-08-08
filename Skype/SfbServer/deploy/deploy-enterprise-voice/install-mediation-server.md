---
title: Instalar os arquivos para o servidor de mediação em Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: Saiba como instalar os arquivos para o servidor de mediação em Skype para Business Server.'
ms.openlocfilehash: b3314e5443a7aa881fa849fd3e3b5b639f72664e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002478"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar os arquivos para o servidor de mediação em Skype para Business Server
 
**Resumo:** Saiba como instalar os arquivos para o servidor de mediação em Skype para Business Server.
  
Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.
  
Use as etapas neste tópico para executar o Skype para o Assistente de implantação de servidor de negócios instalar os arquivos para o servidor de mediação em um computador que você adicionou a um pool do servidor de mediação, depois que você tiver usado o construtor de topologias para definir e publicar o pool. Ao instalar os arquivos do servidor de mediação, você também instala e atribuir o certificado necessário para cada computador em um pool do servidor de mediação. 
  
> [!NOTE]
> Este tópico pressupõe que você já definiu e publicados de um pool do servidor de mediação autônomo em sua topologia, conforme descrito em [implantar um servidor de mediação no construtor de topologia no Skype para Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1. Na mídia de instalação, clique com o botão _ \<mídia de instalação\> _ **\setup\amd64\setup.exe.** e clique em **Executar como administrador**.
    
2. Na página **Local de instalação**, clique em **OK**.
    
3. Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)
    
4. Na página **Skype para o Assistente de implantação do Business Server** , clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**.
    
5. Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.
    
6. Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.
    
7. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
8. Próximo ao **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Executar**e, em seguida, clique em **Avançar**.
    
9. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribuí-lo.
    
11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.
    
12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.
    
13. No computador onde você está executando o Skype para painel de controle do Business Server, verifique se na página **topologia** do Skype para painel de controle do servidor de negócios que o status do serviço do servidor de mediação é mostrado como uma marca de seleção verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**. 
    
Se você adicionou mais de um computador para o pool do servidor de mediação, execute as etapas neste procedimento em todos os outros computadores no pool do servidor de mediação. Se você não precisará instalar arquivos para o servidor de mediação para todos os outros computadores, siga os procedimentos em [Configure troncos no Skype para Business Server](configure-trunks.md) para definir configurações para a conexão de tronco entre este pool de servidor de mediação (ou todos os de mediação Servidores em um site) e seu ponto.

