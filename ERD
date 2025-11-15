import React, { useState } from 'react';
import { Database, Table, Key, Link, ZoomIn, ZoomOut, Download } from 'lucide-react';

const NaseejERD = () => {
  const [zoom, setZoom] = useState(1);
  const [selectedTable, setSelectedTable] = useState(null);

  const tables = [
    {
      id: 'admins',
      name: 'admins',
      x: 50,
      y: 50,
      color: '#ef4444',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'email', type: 'VARCHAR(255)' },
        { name: 'password', type: 'VARCHAR(255)' },
        { name: 'name', type: 'VARCHAR(100)' },
        { name: 'phone_number', type: 'VARCHAR(20)' },
        { name: 'role', type: 'ENUM' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'last_login', type: 'TIMESTAMP' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'stores',
      name: 'stores',
      x: 50,
      y: 380,
      color: '#3b82f6',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'name', type: 'VARCHAR(100)' },
        { name: 'address', type: 'TEXT' },
        { name: 'phone', type: 'VARCHAR(20)' },
        { name: 'email', type: 'VARCHAR(255)' },
        { name: 'latitude', type: 'DECIMAL(10,8)' },
        { name: 'longitude', type: 'DECIMAL(11,8)' },
        { name: 'image_url', type: 'VARCHAR(500)' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'manager_name', type: 'VARCHAR(100)' },
        { name: 'manager_phone', type: 'VARCHAR(20)' },
        { name: 'opening_time', type: 'TIME' },
        { name: 'closing_time', type: 'TIME' },
        { name: 'working_days', type: 'JSON' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'categories',
      name: 'categories',
      x: 400,
      y: 50,
      color: '#10b981',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'name', type: 'VARCHAR(100)' },
        { name: 'description', type: 'TEXT' },
        { name: 'image_url', type: 'VARCHAR(500)' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'order', type: 'INT' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'products',
      name: 'products',
      x: 400,
      y: 280,
      color: '#10b981',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'category_id', type: 'FK', key: true },
        { name: 'name', type: 'VARCHAR(200)' },
        { name: 'description', type: 'TEXT' },
        { name: 'price', type: 'DECIMAL(10,2)' },
        { name: 'discount_price', type: 'DECIMAL(10,2)' },
        { name: 'stock', type: 'INT' },
        { name: 'images', type: 'JSON' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'specifications', type: 'JSON' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'customers',
      name: 'customers',
      x: 750,
      y: 50,
      color: '#f59e0b',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'name', type: 'VARCHAR(100)' },
        { name: 'email', type: 'VARCHAR(255)' },
        { name: 'phone', type: 'VARCHAR(20)' },
        { name: 'password', type: 'VARCHAR(255)' },
        { name: 'profile_image', type: 'VARCHAR(500)' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'total_orders', type: 'INT' },
        { name: 'total_spent', type: 'DECIMAL(10,2)' },
        { name: 'last_order_date', type: 'TIMESTAMP' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'customer_addresses',
      name: 'customer_addresses',
      x: 750,
      y: 370,
      color: '#f59e0b',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'customer_id', type: 'FK', key: true },
        { name: 'street', type: 'TEXT' },
        { name: 'city', type: 'VARCHAR(100)' },
        { name: 'state', type: 'VARCHAR(100)' },
        { name: 'zip_code', type: 'VARCHAR(20)' },
        { name: 'country', type: 'VARCHAR(100)' },
        { name: 'latitude', type: 'DECIMAL(10,8)' },
        { name: 'longitude', type: 'DECIMAL(11,8)' },
        { name: 'is_default', type: 'BOOLEAN' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'delivery_men',
      name: 'delivery_men',
      x: 50,
      y: 750,
      color: '#8b5cf6',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'store_id', type: 'FK', key: true },
        { name: 'name', type: 'VARCHAR(100)' },
        { name: 'email', type: 'VARCHAR(255)' },
        { name: 'phone', type: 'VARCHAR(20)' },
        { name: 'password', type: 'VARCHAR(255)' },
        { name: 'profile_image', type: 'VARCHAR(500)' },
        { name: 'vehicle_type', type: 'VARCHAR(50)' },
        { name: 'vehicle_number', type: 'VARCHAR(50)' },
        { name: 'status', type: 'ENUM' },
        { name: 'is_active', type: 'BOOLEAN' },
        { name: 'rating', type: 'DECIMAL(3,2)' },
        { name: 'total_deliveries', type: 'INT' },
        { name: 'current_latitude', type: 'DECIMAL(10,8)' },
        { name: 'current_longitude', type: 'DECIMAL(11,8)' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'orders',
      name: 'orders',
      x: 400,
      y: 600,
      color: '#ec4899',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'order_number', type: 'VARCHAR(50)' },
        { name: 'customer_id', type: 'FK', key: true },
        { name: 'delivery_man_id', type: 'FK', key: true },
        { name: 'store_id', type: 'FK', key: true },
        { name: 'customer_name', type: 'VARCHAR(100)' },
        { name: 'customer_email', type: 'VARCHAR(255)' },
        { name: 'customer_phone', type: 'VARCHAR(20)' },
        { name: 'subtotal', type: 'DECIMAL(10,2)' },
        { name: 'tax', type: 'DECIMAL(10,2)' },
        { name: 'delivery_fee', type: 'DECIMAL(10,2)' },
        { name: 'total', type: 'DECIMAL(10,2)' },
        { name: 'status', type: 'ENUM' },
        { name: 'payment_status', type: 'ENUM' },
        { name: 'payment_method', type: 'VARCHAR(50)' },
        { name: 'delivery_address', type: 'JSON' },
        { name: 'delivery_man_name', type: 'VARCHAR(100)' },
        { name: 'notes', type: 'TEXT' },
        { name: 'created_at', type: 'TIMESTAMP' },
        { name: 'updated_at', type: 'TIMESTAMP' },
        { name: 'delivered_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'order_items',
      name: 'order_items',
      x: 400,
      y: 1050,
      color: '#ec4899',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'order_id', type: 'FK', key: true },
        { name: 'product_id', type: 'FK', key: true },
        { name: 'product_name', type: 'VARCHAR(200)' },
        { name: 'product_image', type: 'VARCHAR(500)' },
        { name: 'quantity', type: 'INT' },
        { name: 'price', type: 'DECIMAL(10,2)' },
        { name: 'total', type: 'DECIMAL(10,2)' },
        { name: 'created_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'notifications',
      name: 'notifications',
      x: 1100,
      y: 50,
      color: '#06b6d4',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'admin_id', type: 'FK', key: true },
        { name: 'title', type: 'VARCHAR(200)' },
        { name: 'message', type: 'TEXT' },
        { name: 'type', type: 'ENUM' },
        { name: 'data', type: 'JSON' },
        { name: 'is_read', type: 'BOOLEAN' },
        { name: 'created_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'admin_sessions',
      name: 'admin_sessions',
      x: 1100,
      y: 300,
      color: '#06b6d4',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'admin_id', type: 'FK', key: true },
        { name: 'token', type: 'VARCHAR(500)' },
        { name: 'ip_address', type: 'VARCHAR(45)' },
        { name: 'user_agent', type: 'TEXT' },
        { name: 'expires_at', type: 'TIMESTAMP' },
        { name: 'created_at', type: 'TIMESTAMP' }
      ]
    },
    {
      id: 'activity_logs',
      name: 'activity_logs',
      x: 1100,
      y: 520,
      color: '#06b6d4',
      fields: [
        { name: 'id', type: 'PK', key: true },
        { name: 'admin_id', type: 'FK', key: true },
        { name: 'action', type: 'VARCHAR(100)' },
        { name: 'entity_type', type: 'VARCHAR(50)' },
        { name: 'entity_id', type: 'BIGINT' },
        { name: 'description', type: 'TEXT' },
        { name: 'ip_address', type: 'VARCHAR(45)' },
        { name: 'created_at', type: 'TIMESTAMP' }
      ]
    }
  ];

  const relationships = [
    // Products -> Categories
    { from: 'products', to: 'categories', type: 'many-to-one', constraint: 'RESTRICT', label: 'belongs to' },
    
    // Customer Addresses -> Customers
    { from: 'customer_addresses', to: 'customers', type: 'many-to-one', constraint: 'CASCADE', label: 'belongs to' },
    
    // Orders -> Customers
    { from: 'orders', to: 'customers', type: 'many-to-one', constraint: 'RESTRICT', label: 'placed by' },
    
    // Orders -> Delivery Men
    { from: 'orders', to: 'delivery_men', type: 'many-to-one', constraint: 'SET NULL', label: 'delivered by' },
    
    // Orders -> Stores
    { from: 'orders', to: 'stores', type: 'many-to-one', constraint: 'SET NULL', label: 'from' },
    
    // Order Items -> Orders
    { from: 'order_items', to: 'orders', type: 'many-to-one', constraint: 'CASCADE', label: 'belongs to' },
    
    // Order Items -> Products
    { from: 'order_items', to: 'products', type: 'many-to-one', constraint: 'RESTRICT', label: 'contains' },
    
    // Delivery Men -> Stores
    { from: 'delivery_men', to: 'stores', type: 'many-to-one', constraint: 'SET NULL', label: 'assigned to' },
    
    // Notifications -> Admins
    { from: 'notifications', to: 'admins', type: 'many-to-one', constraint: 'CASCADE', label: 'sent to' },
    
    // Admin Sessions -> Admins
    { from: 'admin_sessions', to: 'admins', type: 'many-to-one', constraint: 'CASCADE', label: 'belongs to' },
    
    // Activity Logs -> Admins
    { from: 'activity_logs', to: 'admins', type: 'many-to-one', constraint: 'SET NULL', label: 'performed by' }
  ];

  const getTablePosition = (tableId) => {
    const table = tables.find(t => t.id === tableId);
    return table ? { x: table.x, y: table.y } : { x: 0, y: 0 };
  };

  const drawRelationship = (rel) => {
    const fromPos = getTablePosition(rel.from);
    const toPos = getTablePosition(rel.to);
    
    const fromX = fromPos.x + 150;
    const fromY = fromPos.y + 100;
    const toX = toPos.x + 150;
    const toY = toPos.y + 100;

    const midX = (fromX + toX) / 2;
    const midY = (fromY + toY) / 2;

    let color = '#64748b';
    if (rel.constraint === 'CASCADE') color = '#ef4444';
    if (rel.constraint === 'RESTRICT') color = '#f59e0b';
    if (rel.constraint === 'SET NULL') color = '#8b5cf6';

    return (
      <g key={`${rel.from}-${rel.to}`}>
        <line
          x1={fromX}
          y1={fromY}
          x2={toX}
          y2={toY}
          stroke={color}
          strokeWidth="2"
          strokeDasharray={rel.type === 'many-to-one' ? '5,5' : '0'}
          markerEnd="url(#arrowhead)"
        />
        <circle cx={fromX} cy={fromY} r="4" fill={color} />
        <text
          x={midX}
          y={midY - 5}
          fontSize="11"
          fill={color}
          fontWeight="600"
          textAnchor="middle"
        >
          {rel.constraint}
        </text>
      </g>
    );
  };

  return (
    <div className="w-full h-screen bg-slate-50 flex flex-col">
      {/* Header */}
      <div className="bg-white shadow-md p-4 flex items-center justify-between">
        <div className="flex items-center gap-3">
          <Database className="w-8 h-8 text-blue-600" />
          <div>
            <h1 className="text-2xl font-bold text-gray-800">Naseej Database ERD</h1>
            <p className="text-sm text-gray-600">Entity Relationship Diagram</p>
          </div>
        </div>
        
        <div className="flex items-center gap-4">
          <div className="flex items-center gap-2 bg-slate-100 px-4 py-2 rounded-lg">
            <button
              onClick={() => setZoom(Math.max(0.5, zoom - 0.1))}
              className="p-1 hover:bg-white rounded"
            >
              <ZoomOut className="w-5 h-5" />
            </button>
            <span className="font-mono text-sm w-12 text-center">{(zoom * 100).toFixed(0)}%</span>
            <button
              onClick={() => setZoom(Math.min(2, zoom + 0.1))}
              className="p-1 hover:bg-white rounded"
            >
              <ZoomIn className="w-5 h-5" />
            </button>
          </div>
          
          <button className="flex items-center gap-2 bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700">
            <Download className="w-4 h-4" />
            Export
          </button>
        </div>
      </div>

      {/* Legend */}
      <div className="bg-white border-b px-4 py-2 flex gap-6 text-sm">
        <div className="flex items-center gap-2">
          <div className="w-4 h-4 bg-red-500 rounded"></div>
          <span>CASCADE Delete</span>
        </div>
        <div className="flex items-center gap-2">
          <div className="w-4 h-4 bg-orange-500 rounded"></div>
          <span>RESTRICT</span>
        </div>
        <div className="flex items-center gap-2">
          <div className="w-4 h-4 bg-purple-500 rounded"></div>
          <span>SET NULL</span>
        </div>
        <div className="flex items-center gap-2">
          <Key className="w-4 h-4 text-yellow-600" />
          <span>Primary/Foreign Key</span>
        </div>
        <div className="ml-auto text-gray-600">
          <span className="font-semibold">{tables.length}</span> Tables | 
          <span className="font-semibold ml-2">{relationships.length}</span> Relations
        </div>
      </div>

      {/* ERD Canvas */}
      <div className="flex-1 overflow-auto">
        <svg
          width="1400"
          height="1300"
          style={{ transform: `scale(${zoom})`, transformOrigin: 'top left' }}
          className="bg-slate-50"
        >
          <defs>
            <marker
              id="arrowhead"
              markerWidth="10"
              markerHeight="10"
              refX="9"
              refY="3"
              orient="auto"
            >
              <polygon points="0 0, 10 3, 0 6" fill="#64748b" />
            </marker>
          </defs>

          {/* Draw relationships */}
          {relationships.map(rel => drawRelationship(rel))}

          {/* Draw tables */}
          {tables.map(table => (
            <g
              key={table.id}
              transform={`translate(${table.x}, ${table.y})`}
              onClick={() => setSelectedTable(table.id === selectedTable ? null : table.id)}
              className="cursor-pointer"
            >
              {/* Table Container */}
              <rect
                width="300"
                height={Math.max(200, 30 + table.fields.length * 22)}
                fill="white"
                stroke={table.color}
                strokeWidth={selectedTable === table.id ? "3" : "2"}
                rx="8"
                className="transition-all"
                style={{
                  filter: selectedTable === table.id ? 'drop-shadow(0 4px 12px rgba(0,0,0,0.15))' : 'drop-shadow(0 2px 4px rgba(0,0,0,0.1))'
                }}
              />

              {/* Table Header */}
              <rect
                width="300"
                height="40"
                fill={table.color}
                rx="8"
              />
              <rect
                width="300"
                height="32"
                y="8"
                fill={table.color}
              />

              <text
                x="150"
                y="27"
                fontSize="16"
                fontWeight="bold"
                fill="white"
                textAnchor="middle"
              >
                <tspan>📊</tspan> {table.name}
              </text>

              {/* Table Fields */}
              {table.fields.slice(0, 10).map((field, idx) => (
                <g key={idx}>
                  {idx > 0 && (
                    <line
                      x1="10"
                      y1={50 + idx * 22}
                      x2="290"
                      y2={50 + idx * 22}
                      stroke="#e2e8f0"
                      strokeWidth="1"
                    />
                  )}
                  <text
                    x="15"
                    y={68 + idx * 22}
                    fontSize="12"
                    fill={field.key ? table.color : '#334155'}
                    fontWeight={field.key ? 'bold' : 'normal'}
                  >
                    {field.key && '🔑 '}
                    {field.name}
                  </text>
                  <text
                    x="285"
                    y={68 + idx * 22}
                    fontSize="10"
                    fill="#64748b"
                    textAnchor="end"
                  >
                    {field.type}
                  </text>
                </g>
              ))}

              {table.fields.length > 10 && (
                <text
                  x="150"
                  y={68 + 10 * 22}
                  fontSize="11"
                  fill="#64748b"
                  textAnchor="middle"
                  fontStyle="italic"
                >
                  +{table.fields.length - 10} more fields...
                </text>
              )}
            </g>
          ))}
        </svg>
      </div>

      {/* Table Info Panel */}
      {selectedTable && (
        <div className="bg-white border-t p-4">
          <div className="max-w-4xl mx-auto">
            <h3 className="text-lg font-bold mb-2">
              Table: {tables.find(t => t.id === selectedTable)?.name}
            </h3>
            <div className="grid grid-cols-3 gap-4 text-sm">
              <div>
                <span className="font-semibold">Total Fields:</span> {tables.find(t => t.id === selectedTable)?.fields.length}
              </div>
              <div>
                <span className="font-semibold">Foreign Keys:</span> {tables.find(t => t.id === selectedTable)?.fields.filter(f => f.type === 'FK').length}
              </div>
              <div>
                <span className="font-semibold">Relations:</span> {relationships.filter(r => r.from === selectedTable || r.to === selectedTable).length}
              </div>
            </div>
          </div>
        </div>
      )}
    </div>
  );
};

export default NaseejERD;
