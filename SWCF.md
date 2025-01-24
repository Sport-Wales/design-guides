# Sport Wales Component Functionality Guide (SWCF)

## Form Interaction Patterns

### Input Fields
```jsx
// Standard Implementation
const [value, setValue] = useState('');
const [error, setError] = useState('');

// Input with validation and transformation
<input
  value={value}
  onChange={(e) => setValue(e.target.value.toUpperCase())} // Transform if needed
  className="sw-input w-full"
  aria-invalid={!!error}
  aria-describedby={error ? `${id}-error` : undefined}
/>

// Error Display
{error && (
  <div className="sw-notice text-[--color-sw-red]" id={`${id}-error`}>
    <p className="font-semibold">{error}</p>
  </div>
)}
```

### Checkbox Groups
```jsx
// State Management
const [selectedItems, setSelectedItems] = useState([]);

// Selection Handler
const handleSelection = (itemId) => {
  setSelectedItems(prev => {
    // Handle mutually exclusive options
    if (itemId === 'none') {
      return ['none'];
    }
    
    // Handle multiple selections
    const newSelection = prev.includes(itemId)
      ? prev.filter(id => id !== itemId)
      : [...prev.filter(id => id !== 'none'), itemId];
      
    return newSelection;
  });
};

// Implementation
<div className="grid grid-cols-2 gap-6">
  {items.map((item) => (
    <div key={item.id} className="flex items-center space-x-3">
      <input
        type="checkbox"
        id={item.id}
        checked={selectedItems.includes(item.id)}
        onChange={() => handleSelection(item.id)}
        className="sw-checkbox"
      />
      <label htmlFor={item.id}>{item.label}</label>
    </div>
  ))}
</div>
```

### Mode Toggles
```jsx
// State Management
const [mode, setMode] = useState('default');

// Toggle Implementation
<div className="flex flex-col sm:flex-row gap-4">
  {modes.map((option) => (
    <button
      key={option.id}
      onClick={() => setMode(option.id)}
      className={`
        sw-button flex-1 min-h-[56px]
        ${mode === option.id 
          ? 'sw-button-primary scale-105' 
          : 'bg-white border-2 hover:scale-102'
        }
      `}
    >
      {option.label}
    </button>
  ))}
</div>
```

## Responsive Layout Patterns

### Grid Layout System
```jsx
// Basic Responsive Grid
<div className="grid grid-cols-1 lg:grid-cols-3 gap-6 p-8">
  {/* Main Content */}
  <div className="lg:col-span-2 space-y-8">
    <MainContent />
  </div>
  
  {/* Sidebar */}
  <div className="lg:col-span-1 space-y-6">
    <Sidebar />
  </div>
</div>

// Nested Grid for Form Elements
<div className="grid grid-cols-1 sm:grid-cols-2 gap-6">
  {formItems.map(item => (
    <FormField key={item.id} {...item} />
  ))}
</div>
```

### Mobile-First Patterns
```jsx
// Stack to Row Layout
<div className="flex flex-col sm:flex-row gap-4">
  <div className="w-full sm:w-1/2">
    <ContentBlock />
  </div>
</div>

// Responsive Text
<h2 className="text-xl sm:text-2xl lg:text-3xl">
  Responsive Heading
</h2>

// Responsive Spacing
<div className="p-4 sm:p-6 lg:p-8">
  <Content />
</div>
```

## State Management Patterns

### Form Validation
```jsx
const validateInputs = () => {
  const newErrors = {};
  
  // Required Field Validation
  if (!value) {
    newErrors.field = 'This field is required';
  }
  
  // Custom Validation
  if (value && !customValidation(value)) {
    newErrors.field = 'Invalid format';
  }
  
  // Number Range Validation
  if (number < min || number > max) {
    newErrors.number = `Value must be between ${min} and ${max}`;
  }
  
  setErrors(newErrors);
  return Object.keys(newErrors).length === 0;
};
```

### Calculation Pattern
```jsx
// React hook for calculations
const useCalculation = (inputs) => {
  const [result, setResult] = useState(null);
  
  useEffect(() => {
    if (!validateInputs()) return;
    
    // Perform calculations
    const calculated = performCalculation(inputs);
    
    // Update results
    setResult(calculated);
  }, [inputs]);
  
  return result;
};
```

## User Experience Patterns

### Loading States
```jsx
// Component with Loading State
const [isLoading, setIsLoading] = useState(false);

// Loading Implementation
{isLoading ? (
  <div className="sw-loading-spinner" />
) : (
  <ComponentContent />
)}

// Async Operation Pattern
const handleSubmit = async () => {
  setIsLoading(true);
  try {
    await submitData();
  } finally {
    setIsLoading(false);
  }
};
```

### Error Handling
```jsx
// Error State Management
const [error, setError] = useState(null);

// Error Display Pattern
{error && (
  <div className="sw-notice text-[--color-sw-red]">
    <p className="font-semibold">{error}</p>
    <button 
      onClick={() => setError(null)}
      className="text-sm underline"
    >
      Try Again
    </button>
  </div>
)}
```

### Progressive Disclosure
```jsx
// Conditional Content Display
const [showDetails, setShowDetails] = useState(false);

<div>
  <button 
    onClick={() => setShowDetails(!showDetails)}
    className="sw-button"
  >
    {showDetails ? 'Show Less' : 'Show More'}
  </button>
  
  {showDetails && (
    <div className="mt-4">
      <DetailedContent />
    </div>
  )}
</div>
```

## Accessibility Implementation

### Keyboard Navigation
```jsx
// Focus Management
const handleKeyDown = (e) => {
  if (e.key === 'Enter' || e.key === ' ') {
    e.preventDefault();
    handleAction();
  }
};

// Implementation
<button
  onKeyDown={handleKeyDown}
  className="sw-button"
  aria-label="Descriptive action"
>
  Button Text
</button>
```

### Screen Reader Considerations
```jsx
// Status Updates
const [status, setStatus] = useState('');

<div 
  role="status" 
  aria-live="polite" 
  className="sr-only"
>
  {status}
</div>

// Form Labels
<label 
  htmlFor="input-id" 
  className="sw-label"
>
  <span className="sr-only">Required field: </span>
  Label Text
</label>
```


## Best Practices

1. State Management
   - Keep state as local as possible
   - Use controlled components for form elements
   - Implement proper error boundary handling

2. User Experience
   - Provide immediate feedback for user actions
   - provide helper tool tips 
   - Maintain consistent interaction patterns
   - Implement proper loading states
   - Always design for moblie experience 
   - Optimize for mobile devices

3. Performance
   - Optimise re-renders
   - Limit the number of re-rendering as possible 
   - Implement proper memoization
   - Use efficient event handlers
