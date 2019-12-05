---
title: Suporte à migração da Unificação de Mensagens do Exchange Online
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A Microsoft está desativando o serviço online de Unificação de mensagens do Exchange (ExchUMO) em fevereiro de 2020. Este artigo resume o que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
ms.openlocfilehash: 6fe0436d0ae4df2b4eb56a3c84319770b45f3139
ms.sourcegitcommit: b8e16703e4611ca2bde55896ec158b33be4f9ba0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39842463"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Suporte à migração da Unificação de Mensagens do Exchange Online

Em referência ao [anúncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) em 8 de fevereiro de 2019, a Microsoft está desativando o serviço do Exchange Unified Messaging online (ExchUMO) até 2020 de fevereiro. Este artigo oferece um resumo do que os clientes afetados devem saber e fazer para planejar sua continuidade de negócios.
 
O ExchUMO é implantado por clientes para correio de voz, atendedor automático, fila de chamadas e serviços de integração de fax. A Microsoft planeja ajudar os clientes a migrar para serviços de sistema telefônico que já dão suporte a milhares de clientes no Skype for Business Online e no Microsoft Teams.

O correio de voz é basicamente uma migração orientada pela Microsoft; o envolvimento do administrador e/ou o investimento podem ser necessários para um subconjunto de clientes. O atendedor automático é uma migração orientada por administradores; Você precisará recriar as árvores de atendedor automático do ExchUMO no serviço de nuvem do atendedor automático na nuvem. Os clientes que consomem qualquer um dos recursos do ExchUMO com um PBX de terceiros não serão migrados para os serviços de nuvem da Skype porque não dão suporte a sistemas PBX de terceiros. Um plano de aposentadoria para suporte a terceiros foi anunciado neste [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), e os clientes neste modelo de implantação podem migrar os usuários para um dos serviços/plataformas de comunicação unificada da Microsoft ou adquirir uma solução de correio de voz e/ou atendedor automático de terceiros para esses usuários. Não há suporte para a integração de fax nos serviços baseados em nuvem; Os clientes precisarão migrar para uma solução de terceiros.

### <a name="who-is-affected"></a>Quem é afetado?

Os clientes que estão consumindo qualquer um dos seguintes recursos do serviço online de Unificação de mensagens do Exchange são afetados:

- Serviço de correio de voz
- Serviço de atendedor automático
- Serviço de fila de chamadas
- Integração de fax

> [!Note]
> Os clientes que usam qualquer um dos servidores Exchange no local com Unificação de mensagens não são afetados. 

Saiba mais sobre o impacto da experiência do usuário e do administrador no [impacto da experiência do usuário](#user-experience-impact).

## <a name="migration-plan-overview"></a>Visão geral do plano de migração

A Microsoft identificou várias implantações de clientes que estão consumindo recursos do ExchUMO e ajudará os clientes a migrar com base no plano a seguir. 

|Grupo de clientes |Cronológica  |Detalhes  |
|---------|---------|---------|
|Clientes que estão prontos para migrar<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal</ul>   |   Março — maio de 2019  |Exemplos<ul><li>    Clientes com implantação e uso simples de correio de voz<li>Clientes que têm todos os requisitos estabelecidos pela Microsoft para executar a migração<ul>|
|Clientes com pré-requisitos<br><br>Recursos a serem migrados:<br><ul><li>Caixa postal<li>Atendedor Automático<li>Fila de chamadas</ul> |  Maio – 2019 de dezembro |Exemplos <br><ul><li>Configuração híbrida não concluída<li>Os números PSTN híbridos não estão configurados</ul>|
|Clientes que exigem envolvimento da administração & investimento do cliente<br><br>Recursos a serem migrados:<ul><li>caixa<li>Atendedor Automático<li>Filas de chamadas<li>Integração de fax</ul>| Até fevereiro de 2020  | Exemplos <br><ul><li>O serviço ExchUMO é consumido pelo PBX de terceiros<li>Clientes com requisitos de acesso do assinante PSTN<li>Clientes no SFB 2010 (não suportados)<li>Integração de fax</ul> |

## <a name="voicemail-migration-steps"></a>Etapas de migração de correio de voz

1.  **Seja informado**
 
    Familiarize-se com o [anúncio do blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) e este artigo para planejar uma migração tranqüila para seus usuários. Consulte [verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obter detalhes sobre os recursos de correio de voz do sistema telefônico.  
 
2.  **Estabelecer uma topologia híbrida do Skype for Business**

    Se você não tiver uma topologia híbrida do Skype for Business estabelecida, será necessário fazer isso para habilitar uma migração tranqüila dos usuários de correio de voz. Consulte [Configurar o Skype for Business híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obter mais detalhes. 

    > [!Note]
    > Você não precisa migrar os usuários para online para a migração do serviço de correio de voz. No entanto, para que os usuários locais aproveitem o serviço de correio de voz do sistema telefônico, é preciso estabelecer uma topologia híbrida.

3. **Planejar a migração do atendedor automático**
    
    Os administradores podem começar a migrar atendedores automáticos do ExchUMO para o atendedor automático da nuvem a qualquer momento. Consulte [configurar um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obter mais detalhes. A Microsoft continua a fornecer recursos adicionais de atendedor automático que os clientes podem considerar necessários para a migração, os administradores devem avaliar o conjunto de recursos e migrar suas instâncias de atendedor automático de acordo com isso. Para comparação de lista de recursos, consulte a [matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planejar a validação e os testes de correio de voz após a migração**

    A migração de correio de voz é orientada pela Microsoft. Os administradores não precisam fazer nada, uma vez que a topologia híbrida pré-requisito é estabelecida. A Microsoft executa a validação e os testes necessários para garantir que a migração de correio de voz dos usuários não seja interrompida. Os administradores são incentivados a executar testes e validação em seus lados. Consulte [plano de teste sugerido e validação pós-implantação para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para um plano de teste recomendado. 

    > [!Note]
    > Não há suporte para Lync Server 2010. Se você estiver em uma implantação do servidor do 2010, planeje uma atualização do servidor ou considere a migração de seus usuários para o Microsoft Teams ou o Skype for Business online.  

5. **Monitorar o centro de notificações de administração**

    Procure um aviso no centro de notificações de administração com detalhes adicionais e linha do tempo sobre a migração dos seus usuários. As notificações são enviadas pelo menos 30 dias antes do período de migração. 

    > [!Note]
    > Se você recebeu uma notificação com a linha do tempo de migração dos seus usuários e gostaria de adiar a migração para um motivo crítico para os negócios, você pode fazer isso entrando em contato com o suporte da Microsoft. Observe que não é possível adiar a migração para além da data de aposentadoria, de fevereiro de 2020. Para clientes que podem ter mais dúvidas, entre em contato com a equipe da sua conta ou com o suporte da Microsoft. Os clientes que já usam o Office 365 podem enviar um caso de suporte por meio do portal de administração do Office 365. 

6. **Considere optar por uma migração planejada**

    Você pode optar por uma migração planejada do serviço de correio de voz para o CVM. Antes de optar, examine os detalhes deste artigo, especialmente as seguintes seções:

    - Etapas de migração (esta seção)
    - Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure
    - Impacto da experiência do usuário

    Ao escolher uma migração gerenciada, você não receberá uma notificação pré-migração de 30 dias no centro de mensagens do portal de administração do 365 da Microsoft.
 
    Para aceitar uma migração planejada, envie uma solicitação de email do endereço de email do administrador para [CVM@microsoft.com](mailto:cvm@microsoft.com) com as seguintes informações:

    - Data preferida (terças-feiras): as ondas de migração são executadas a cada terça-feira. Selecione uma data em uma terça-feira que não ultrapasse o 12/3/2019.
 
    - ID do locatário: 32 número de caracteres nesse formato 0046728c-688a-4472-a38f-098fec60ac6x. Você pode encontrar sua ID de locatário no portal de administração do Microsoft 365 em Azure AD ou usando o seguinte cmdlet do PowerShell:`Get-CsTenant | Select ObjectId`
 
    Você receberá uma confirmação de email depois que seu locatário for migrado com sucesso.

## <a name="auto-attendant-migration-guidelines"></a>Diretrizes de migração do atendedor automático

Os administradores do locatário do Office 365 são obrigados a recriar seus atendedores automáticos online do Exchange UM no serviço de atendedor automático do Microsoft Cloud e alternar os números de telefone locais para eles antes de 1 ° de fevereiro de 2020, que é quando o serviço do Exchange UMO será continua. Esta é a diretriz recomendada para migrar e testar com êxito novos atendedores automáticos de nuvem. Se você tiver um grande número de atendedores automáticos, poderá usar o [atendedor automático do Exchange um para os scripts de migração do atendedor automático da nuvem](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) para simplificar a migração em massa de atendedores automáticos.

### <a name="setup"></a>Instalação

Recomendamos que você inicie a configuração de seus novos atendedores automáticos antecipadamente para evitar problemas de último minuto e para se familiarizar com a funcionalidade e a experiência do serviço de atendedor automático na nuvem. Para atendedores automáticos que exigem um ou mais recursos de lacuna, você pode criar e testar atendedores automáticos quando os recursos de lacuna estiverem disponíveis para se preparar para a implantação. Para obter mais informações sobre os recursos de espaço, consulte o [Apêndice](#appendix).

1. Use os cmdlets do Exchange UMO para exportar a configuração de atendedores automáticos existentes usando [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use o cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) no PowerShell do Exchange Online para exportar os arquivos de mídia de saudação (se usados) e convertê-los em formato. mp3.
3. Siga as instruções em [planejar atendedores automáticos da nuvem](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) e [Configure um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para criar atendedores automáticos usando o centro de administração do Microsoft Teams ou o PowerShell.
4. Revise suas saudações se as opções do menu forem alteradas.
5. Configure transferências para seus grupos de resposta usando a solução alternativa "transferência de chamada de atendedor automático para PSTN" na seção [problemas conhecidos](#known-issues) deste artigo.  
6. Teste os novos atendedores automáticos. Para testar, chame-os internamente ou atribua um número de telefone de teste.  

### <a name="cutover"></a>Transfira

1. Mude os números de telefone dos atendedores automáticos do Exchange UMO para os novos atendedores automáticos.
2. Mova o URI SIP do objeto de contato para a conta do recurso.
3. Teste e valide seus atendedores automáticos usando os números de telefone atribuídos recentemente. 

## <a name="appendix"></a>Anexo

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de recursos de serviços baseados em nuvem do ExchUMO e do Azure

| Atender | Nível do recurso | Recurso | Observações  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VIRTUAIS  | Recursos do serviço| Oferecer suporte a PBX de terceiros    | Incluir todos os recursos fornecidos ao PBX de terceiros, como o MWI (Message Waiting Indicator) usando mensagens de notificação SIP do Exchange UM online | N   | Y    |
| VIRTUAIS | Recursos do serviço  | Suporte para o Skype for Business Server   |  | S | S    |
| VIRTUAIS | Recursos do serviço | Suporte ao Microsoft Teams|  | Y | N    |
| VIRTUAIS | Recursos do serviço | Descoberta eletrônica e retenção  | Para segurança e conformidade  | S | S    |
| VIRTUAIS | Recursos do serviço | Suporte a regras do Exchange | Para segurança e conformidade  | S | S    |
| VIRTUAIS | Recursos do usuário | Acesso de discagem PSTN  | Acesso do assinante  | N | Y    |
| VIRTUAIS | Recursos do usuário | Acesso de voz do Outlook em PSTN   | Acesso do assinante  | N | Y    |
| VIRTUAIS | Recursos do usuário | Discagem usando um ponto de extremidade autenticado | Como chamar o serviço de correio de voz para ouvir mensagens de voz e alterar as configurações de correio de voz| S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para desativar o correio de voz   |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para alterar a saudação pessoal  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para criar uma saudação OOF  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para alterar o idioma padrão  |  | S | S    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para substituir a saudação padrão por TTS  |  | Y | N    |
| VIRTUAIS | Recursos do usuário | Gravar saudações pessoais (dispositivo autenticado) |  | S | S    |
| VIRTUAIS | Recursos do usuário | Gravar mensagens pessoais (PSTN)-tocar no telefone |  | N | Y    |
| VIRTUAIS | Recursos do usuário | Configuração do usuário para desabilitar a transcrição |  | N | Y    |
| VIRTUAIS | Recursos do usuário | Transcrição  |  | Y | S    |
| VIRTUAIS | Recursos do usuário | Caixa postal Visual em todos os pontos de extremidade   | Com o controle de usuário para reproduzir, excluir, indicador de mensagem aguardando e status-alternar, em todos os pontos de extremidade compatíveis  | Y | S    |
| VIRTUAIS | Recursos do usuário | Formato de arquivo de áudio MP3 no Outlook    |  | Y | S    |
| VIRTUAIS | Recursos do usuário | Controle de reprodução de velocidade variável |  | Y | S    |
| VIRTUAIS | Recursos do usuário | Encaminhar um correio de voz  | Encaminhar um correio de voz recebido para outros usuários | Y | S    |
| VIRTUAIS | Recursos do usuário | Enviar uma mensagem de voz para um grupo de usuários  |Transmissão de correio de voz   | N | Y   |
| VIRTUAIS | Recursos do usuário | Notificação de correio de voz usando SMS    | Os usuários podem receber SMS quando tiverem um novo correio de voz    | N | Y    |
| VIRTUAIS | Recursos do usuário | Idiomas de saudação suportados | Detalhes aqui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | S    |
| VIRTUAIS | Recursos do usuário | Regras de atendimento de chamada |  | Y | S    |
| VIRTUAIS | Recursos do usuário | Executar no telefone (PSTN)-para reproduzir mensagem | Ligar para mim na minha célula para ouvir a mensagem de voz  | N | Y    |
| VIRTUAIS | Recursos do usuário | Reproduzir no telefone (auth)-para reproduzir mensagem | Ligar para mim no meu dispositivo autenticado  | Y | S    |
| VIRTUAIS | Recursos do usuário | Caixa de correio compartilhada entre vários usuários |  | Y | S    |
| VIRTUAIS | Recursos do chamador  | Experiência de chamadas — correio de voz protegido | O chamador pode escolher uma opção para marcar uma mensagem gravada como protegida| N | Y    |
| VIRTUAIS | Recursos do chamador  | Experiência de chamadas — correio de voz privado | O chamador pode escolher uma opção para marcar uma mensagem gravada como particular  | N | Y    |
| VIRTUAIS | Recursos do chamador  | Detecção de silêncio   |  | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Correio de voz protegido no nível do servidor    | Locatário-o administrador pode configurar uma regra de nível de serviço para marcar o correio de voz recebido como protegido | Y | S    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o limite de tempo de duração da gravação  |     | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o tempo limite de detecção de silêncio    |  | N/D    | Y    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o número de falhas de entrada | CVM: embutido em código para 3 | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Alterar o idioma padrão |  | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Desabilitar/habilitar transcrição |  | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Desabilitar/habilitar a notificação de chamada perdida |  | N | Y    |
| VIRTUAIS | Locatário-recursos de administração | Ajude a Microsoft a melhorar a visualização da caixa postal    |  | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Personalizar mensagem de texto para usuários habilitados|  | N/D    | Y    |
| VIRTUAIS | Locatário-recursos de administração | Mascaramento de obscenidades da transcrição|  | Y | N    |
| VIRTUAIS | Locatário-recursos de administração | Política de correio de voz    |   | S | S    |
| VIRTUAIS | Locatário-recursos de administração | Administração do portal da Web   |  | CY19   | Y    |
| VIRTUAIS | Locatário-recursos de administração | ™   |  | S | S    |
| Altere | Recursos do serviço | AA compatível com PBX de terceiros    |  | N | Y    |
| Altere | Recursos do serviço | Suporte para o Skype for Business Server   |  | S | S    |
| Altere | Recursos do serviço | Suporte ao Microsoft Teams|  | Y | N    |
| Altere | Recursos do serviço | Discar por nome, entrada DTMF    |  | S | S    |
| Altere | Recursos do serviço | Discar por nome, entrada de fala  |  | S | S    |
| Altere | Recursos do serviço | Suporte a vários idiomas | Detalhes da linguagem aqui:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| Altere | Recursos do serviço | Transferir para o Operator, o CQ ou um usuário |  | S | S    |
| Altere | Recursos do serviço | Transferir para o número PSTN internamente (RNL)  |  | S | S    |
| Altere | Recursos do serviço | Transferir para o número PSTN externamente  |  | Veja a seção problemas conhecidos abaixo | Y    |
| Altere | Recursos do serviço | Horário comercial |  | S | S    |
| Altere | Recursos do serviço | Opções do menu | Opções do menu IVR  | S | S    |
| Altere | Recursos do serviço | Atribuindo um número PSTN à nuvem para AA |  | Y | N    |
| Altere | Recursos do serviço | Atribuindo um número PSTN local a AA  |  | S | S    |
| Altere | Recursos do serviço | Seleção de usuário personalizada  | Como habilitar os chamadores para acessar a lista personalizada de usuários da organização| S | S    |
| Altere | Recursos do serviço | Tratamento de horas extras e feriados  |  | S | S    |
| Altere | Recursos do serviço | Saudação personalizada usando texto para fala  |  | S | S    |
| Altere | Recursos do serviço | Discagem de extensão   | Como alcançar um usuário ao discar a extensão dele  | S   | S    |
| Altere | Recursos do serviço | Caixa de correio para chamadores AA para deixar uma mensagem    |  | CY19   | Y    |
| Altere | Recursos do serviço | Várias atribuições de números PSTN a um AA|  | S | S    |
| Altere | Locatário-recursos de administração | Administração do portal da Web   |  | Y | N    |
| Altere | Locatário-recursos de administração | Cmdlets do PowerShell  |  | S | S    |
| Fax| Recursos do serviço | Integração de fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plano de teste sugerido e validação após a migração para administradores

Para confirmar se os usuários foram migrados para o correio de voz na nuvem, deixe um correio de voz para um usuário e verifique o corpo da mensagem no Outlook.  As mensagens de correio de voz na nuvem têm um rodapé que lê:

**Obrigado por usar a transcrição! Se você não vir uma transcrição acima, é porque a qualidade do áudio não era clara o suficiente para transcrever.**

Ao testar a funcionalidade de correio de voz após a migração dos usuários, considere os seguintes cenários:

- Valide o acesso ao correio de voz entre todos os tipos de ponto de extremidade em sua organização: aplicativos e telefones IP. 
- Valide com os usuários de exemplo que as saudações personalizadas configuradas são jogadas aos chamadores.   
- Se a sua organização tiver uma exigência legal ou de conformidade para desativar a transcrição para os usuários, verifique se ela está desabilitada após a migração. Para obter mais detalhes, consulte [Configurar correio de voz na nuvem](/microsoftteams/set-up-phone-system-voicemail).
- Se você configurou anteriormente políticas e políticas de VM do Exchange, certifique-se de que elas estejam em vigor.
- Familiarize-se com os cmdlets do PowerShell do serviço de correio de voz na nuvem para alterar configurações do usuário.  

### <a name="user-experience-impact"></a>Impacto da experiência do usuário

Veja a seguir uma visão geral da experiência de migração de correio de voz do usuário final.


|Enfrente  |Alteração na experiência do usuário|
|---------|---------|
|Notificação por email | Nenhuma alteração<br>Nenhum e-mail é enviado aos usuários notificando sobre a ativação/migração da conta de correio de voz. |
|Acesso às mensagens anteriores | Nenhuma alteração<br>Os usuários têm acesso às mensagens de correio de voz anteriores em todos os pontos de extremidade compatíveis. |
|Recebendo VM no Outlook, aplicativos SFB| Nenhuma alteração<br>Os usuários continuam recebendo mensagens de correio de voz em todos os pontos de extremidade compatíveis. |
|Transcrição | Aumento<br>A transcrição CVM tem uma taxa de precisão muito mais alta e idiomas com suporte do que o ExchUMO. |
|Configuração do usuário | Nova experiência<br>Os usuários podem alterar suas preferências em um portal de configuração de usuário (USP). Os usuários podem acessar o USP a partir de um hiperlink no email de correio de voz ou o botão de configurações do usuário no cliente do SFB; https://aka.ms/vmsettings.   
 |Recursos| Para obter detalhes, consulte a comparação de conjuntos de recursos. |
|Regras do Outlook para mensagens VM | Nenhuma alteração<br>As regras criadas anteriormente serão aplicadas às mensagens CVM após a migração.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gerenciamento e provisionamento de usuários no CVM

Os novos usuários do Skype for Business serão provisionados automaticamente para o correio de voz na nuvem quando criados. Não é preciso qualquer trabalho ou licença de administrador adicional para fornecer novos usuários de correio de voz. Consulte [Configurar o correio de voz na nuvem](/microsoftteams/set-up-phone-system-voicemail) para saber mais sobre o gerenciamento de políticas para usuários novos e existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiência de gerenciamento do atendedor automático do administrador

Para saber mais sobre atendedores automáticos, consulte [configurar um atendedor automático na nuvem](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### <a name="known-issues"></a>Problemas conhecidos

**Transferência de chamada de atendedor automático para PSTN** Os clientes são incentivados a configurar uma solução temporária para atender aos requisitos de transferência de uma chamada de atendedor automático para um número de PSTN externo ou para uma instância de RGS. 
 
Um problema foi identificado durante a garantia de qualidade com o recurso transferir para o número PSTN, que não será corrigido no tempo para que os clientes comecem a migrar o serviço Exchange UMO antes da data de aposentadoria agendada de 1 de fevereiro de 2020. Como solução alternativa, os administradores podem transferir chamadores de atendedor automático para um usuário virtual local com uma configuração de encaminhamento de chamada ativa para o número de telefone PSTN ou o número de telefone do RGS. 
 
Experiência esperada
- Os administradores não precisam licenciar o usuário virtual, uma vez que esta solução alternativa 
- Os administradores podem manipular a identificação de chamadas que o receptor PSTN verá ao atribuir o número desejado ao usuário virtual ou usar os recursos de manipulação de dígitos de SBC
- Os chamadores PSTN não sofrerão atraso durante a transferência de chamadas e continuarão a ver a identificação de chamadas do atendedor automático após a transferência ser bem-sucedida  

**Caixa de correio compartilhada:** Uma caixa de correio compartilhada que é configurada usando o Exchange UM online continuará a receber mensagens depois de migrar para o CVM e continuará a ser acessada pelos usuários via Outlook. No entanto, o acesso para alterar as mensagens de saudação dessas caixas de correio não estará disponível após a migração para o CVM. Os clientes com caixas de correio compartilhadas que são usadas para capturar chamadores de atendedor automáticos devem aproveitar os recursos de caixa de correio de atendedores automáticos e filas de caixa de correio compartilhadas depois de lançado (ETA de 2019 outubro
  
**Atualize para a faixa do teams no cliente SFB:** O serviço CVM é baseado na infraestrutura do Microsoft Teams; as chamadas para o cliente Skype for Business podem fazer com que uma faixa de informações seja exibida no cliente que diz: "username não está usando o Skype for Business. Para uma experiência mais rica, mude para o Microsoft Teams ou inicie uma reunião do Skype. "
Certifique-se de atualizar o cliente Skype for Business dos usuários para a atualização mais recente do cliente do C2R para impedir que essa faixa seja exibida.
  
**Configurar o correio de voz leva você ao OWA:** Clicar em "configurar correio de voz" do cliente continuará a levar os clientes do Skype for Business Server 2015/2013 para a página do portal do Office Web Access (OWA) após a migração para o CVM. Todas as configurações foram removidas da guia correio de voz no OWA, e uma faixa será exibida com um link de redirecionamento para levar os usuários ao portal de configurações do usuário do CVM.
 
**Alterar o acesso móvel à saudação:** O acesso ao Assinante PSTN não é compatível com o CVM. Para os usuários que precisam alterar a saudação remotamente, uma opção de menu "alterar sua saudação" é adicionada ao serviço IVR de correio de voz para clientes móveis. Os usuários podem chamar esse serviço pressionando e mantendo a tecla "1" no teclado de discagem do cliente móvel.
