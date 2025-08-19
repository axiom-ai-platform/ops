from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/guidance', methods=['POST'])
def get_guidance():
    """
    AXIOM Guidance API Endpoint
    """
    data = request.json
    user_query = data.get('userQuery', 'N/A')
    user_role = data.get('userRole', 'N/A')
    current_context = data.get('currentContext', {})

    # 這裡會是我們AI的核心邏輯，但目前先返回預設訊息
    guidance_message = "我已成功接收您的請求。這代表核心服務已啟動。您的查詢是: '{}'".format(user_query)
    suggested_next_steps = [
        {
            "action": "view_status",
            "endpoint": "/api/v1/system/status",
            "description": "API服務已上線，您可以查看系統運行狀態"
        }
    ]

    response = {
        "guidanceMessage": guidance_message,
        "suggestedNextSteps": suggested_next_steps
    }
    return jsonify(response)

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=8080)
