## <a name="integration-models-for-solution-providers"></a>Modelos de integração para provedores de soluções

<a name="steps"></a>

Como provedor de soluções de central de contatos, há três modelos a escolher para integrar sua solução de central de contatos conectada ao Teams:

- Se você quiser usar SBCs certificados e Roteamento Direto para conectar uma solução de central de contatos ao Teams, consulte o Conexão [modelo](?tabs=connect#steps).

- Se você quiser usar bots do Azure e as APIs de Comunicação do Microsoft Graph para permitir que os provedores de soluções criem aplicativos Teams, consulte o modelo [extend .](?tabs=extend#steps)

- Se você quiser usar um SDK que permita que os provedores de soluções insumentem experiências Teams nativas em seu Aplicativo, consulte o [modelo power](?tabs=power#steps). As soluções de energia serão possíveis quando o SDK estiver disponível, no final de 2021.

### <a name="the-connect-model"></a>[**O Conexão modelo**](#tab/connect)

O Conexão usa SBCs certificados pela Microsoft e Roteamento Direto para conectar soluções de contact center Teams infraestrutura do sistema de telefonia, habilitando o roteamento, a configuração e as percepções do sistema aprimoradas.

Os agentes podem configurar assistentes virtuais automatizados e filas de roteamento baseadas em habilidades para coletar informações e conectar clientes com especialistas no assunto.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - Office 365 authN para que os agentes se conectem ao locatário da Microsoft a partir do cliente CCaaS integrado 

  - Veja quando os agentes estão disponíveis com Teams

  - Transferências e suporte a chamada de grupo com Teams 

  - Teams Graph APIs e APIs de Comunicação na Nuvem para integração com Teams 

  - Tronco SIP de vários locatários para dar suporte a vários clientes no SBC do provedor de soluções.  

  - Provedores de soluções para usar o [ <span class="underline">controlador de borda de sessão certificado pela Microsoft (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**O modelo Extend**](#tab/extend)

O modelo Extend se integra ao cliente Teams usando a plataforma cliente [Teams](/microsoftteams/platform/overview), [apIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) Teams Graph e [API de Comunicações](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)na Nuvem no Microsoft Graph . O modelo Extend também usa o sistema Teams telefone para todas as experiências de controle de chamadas e chamadas da central de contatos, e o provedor de soluções do centro de contatos atua como uma operadora de telefonia junto com Microsoft 365.

Os agentes podem usar Teams para colaboração interna e comunicação externa e podem se beneficiar de notas dinâmicas e contextuais correlacionando dados de vários sistemas antes de iniciar um envolvimento e, em seguida, evitar a alternência de contexto custosa.

As organizações podem projetar fluxos de trabalho e configurações de roteamento avançadas para o indivíduo e medir a qualidade de seu sistema e interações.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - Teams Graph APIs e APIs de Comunicação na Nuvem para integração com Teams 

  - Teams aplicativo baseado em agente para experiências de agente 

  - Teams como o ponto de extremidade de chamada principal para os agentes 

  - Teams cliente chamando todos os controles de chamada

  - Aplicativo de experiência do agente para cliente web e móvel Teams web

  - Análise, gerenciamento de fluxo de trabalho, experiências baseadas em função para agentes no aplicativo CCaaS em Teams

  - Experiências de chat e colaboração integradas Teams clientes 

  - Preservar o desempenho e a qualidade Teams experiências do cliente em todos os aplicativos  

### <a name="the-power-model"></a>[**O modelo Power**](#tab/power)

O modelo Power permite que os provedores de soluções criem aplicativos de voz nativos baseados no Azure usando a infraestrutura de chamada Teams e a plataforma de cliente para fornecer soluções modernas e inteligentes para conexão colaborativa de cliente e agente. O objetivo do modelo Power é fornecer uma experiência de central de contatos de um aplicativo com uma tela.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - Experiências de agente formais habilitadas de forma nativa para comunicação omnicanal por meio Teams SDK 

  - Usar Teams de colaboração para colaboração de agentes e interações do cliente  

  - Provisionamento rápido de serviços de nuvem, implantar em qualquer lugar 

  - Controle de conversa direta e interação com os usuários durante Teams conversas 

>[!NOTE]
> O modelo Power estará disponível no final de 2021.
